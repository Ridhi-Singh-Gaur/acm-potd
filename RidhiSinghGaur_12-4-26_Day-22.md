class Pair{
    int x;
    int y;
    public Pair(int x,int y){
        this.x=x;
        this.y=y;
    }
}
class Solution {
    public int numIslands(char[][] grid) {
        boolean[][] visited=new boolean[grid.length][grid[0].length];
        for(int i=0;i<grid.length;i++){
            for(int j=0;j<grid[0].length;j++){
                visited[i][j]=false;
            }
        }
        int c=0;
        for(int i=0;i<grid.length;i++){
            for(int j=0;j<grid[0].length;j++){
               if(grid[i][j]=='1' && visited[i][j]==false){
                c++;
                Queue<Pair> q=new LinkedList<>();
                Pair x=new Pair(i,j);
                q.add(x);
                visited[i][j]=true;
                int[] xcor={0,1,-1,0};
                int[] ycor={1,0,0,-1};
                while(!q.isEmpty()){
                    Pair p=q.remove();
                    for(int k=0;k<4;k++){
                        int xc=p.x+xcor[k];
                        int yc=p.y+ycor[k]; 
                        if(xc>=0 && xc<grid.length && yc>=0 && yc<grid[0].length && grid[xc][yc]=='1' && visited[xc][yc]==false){
                            q.add(new Pair(xc,yc));
                            visited[xc][yc]=true;                        
                        }                   
                    }
                }
               }
            }
        } 
        return c;       
    }
}
<img width="1918" height="1078" alt="image" src="https://github.com/user-attachments/assets/a60eaeb9-b357-4767-b675-10d04712c841" />
