import java.util.*;
class Solution {
    public int findCircleNum(int[][] isConnected) {
        ArrayList<ArrayList<Integer>> x=new ArrayList<>();
        for(int i=0;i<isConnected.length;i++){
            x.add(new ArrayList<Integer>());
        }
        for(int i=0;i<isConnected.length;i++){
            for(int j=0;j<isConnected[i].length;j++){
                if(j!=i && isConnected[i][j]==1){
                    x.get(i).add(j+1);
                }
            }
        }
        int[] visited=new int[isConnected.length+1];
        Queue<Integer> q=new LinkedList<Integer>();
        int count=0;
        for(int i=1;i<=isConnected.length;i++){
            if(visited[i]!=1){
                dfs(x,i,q,visited);
                count++;
            }
        }
        return count;
    }
    public void dfs(ArrayList<ArrayList<Integer>> x,int index,Queue<Integer> q,int[] visited){
        q.add(index);
        visited[index]=1;
        while(!q.isEmpty()){
            int pop=q.remove();
            for(int item:x.get(index-1)){
                if(visited[item]!=1){
                    dfs(x,item,q,visited);
                }
            }
        }
    }
}
<img width="1918" height="1078" alt="image" src="https://github.com/user-attachments/assets/5d2fe3e5-0860-4e1c-8918-0bee085bb7c5" />
