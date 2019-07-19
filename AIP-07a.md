| AIP | Title | Author | Type | Category | Status | Created |
|---|---|---|---|---|---|---|
| 7a | Random | Lucas Nestler | Standards | Peering | In Progress | 4th of July |

Assuming all nodes have equal speeds and every node is aware of every other node, random peering allows for consensus in case of a doublespent to be found within 18 iterations (0.9s assuming everyone has a 50ms ping to everyone else) no matter the size of the network, as seen in basic cellular automatas. 

A simple [processing](https://processing.org) code to test this property has been added below, the resulting animation can be found in consensus.gif.
```
// CONFIG
int asked = 8;      // The number of random nodes to be asked
          // before forming an opinion
int consenus = asked/2; // To agree with other nodes, more than 50%
          // of the asked nodes have to agree on a value X
int size = 1000;    // Total size of the grid (X,Y) in blocks
int blockSize = 2;    // Size of one block (X,Y)

// GLOBAL VARIABLES
int[][] nodes = new int[size][size];
int[][] newNodes = new int[size][size];
color[] colours = {#000000, #FF0000, #00FF00}; 
int colourCount = colours.length-1;

void drawNodes() {
  for (int x=0; x<size; x++) {
    for (int y=0; y<size; y++) {
      fill(colours[nodes[x][y]]);
      rect(x*blockSize, y*blockSize, blockSize, blockSize);
    }
  }
}

void randomizeNodes() {
  for (int x=0; x<size; x++) {
    for (int y=0; y<size; y++) {
      nodes[x][y] = int(1+random(colourCount));
      newNodes[x][y] = 0;
    }
  }
}

void updateNodes() {
  for (int x=0; x<size; x++) {
    for (int y=0; y<size; y++) {
      int[] neighbours = new int[asked]; // Update Node at X/Y
      float[] cols = new float[7];
      float ringSize = 0;
      for (int j=0; j<=asked; j++) cols[nodes[int(random(size))][int(random(size))]]++;
      // Save updated value to new array
      for (int i=1; i<7; i++) if (cols[i]>consenus)newNodes[x][y] = i; 
    }
  }
  // Finalize update (replace old values with new ones)
  for (int x=0; x<size; x++) for (int y=0; y<size; y++) {
    if (newNodes[x][y]>0) nodes[x][y] = newNodes[x][y];
    else if (newNodes[x][y]==-1) nodes[x][y] = 0;
  }
}

void setup() {
  frameRate(30);
  background(0);
  stroke(0);
  strokeWeight(0);
  randomizeNodes();
}
void draw() {
  drawNodes();
  updateNodes();
  saveFrame("####.jpg");
}

void mousePressed() {
  randomizeNodes();
}
```
