class Solution {
    public boolean canFinish(int numCourses, int[][] prerequisites) {
        int[] visited=new int[numCourses];
        List<List<Integer>> adj=new ArrayList<>();
        for(int i=0;i<numCourses;i++){
            List<Integer> l=new ArrayList<>();
            adj.add(new ArrayList<>());
        }
        for(int i=0;i<prerequisites.length;i++){
            adj.get(prerequisites[i][0]).add(prerequisites[i][1]);
        }
        Arrays.fill(visited,0);
        Stack<Integer> s=new Stack<Integer>();
        for(int i=0;i<numCourses;i++){
            if(visited[i]==0){
                dfs(i,adj,visited,s);
            }
        }
        List<Integer> order=new ArrayList<>();
        while(!s.isEmpty()){
            order.add(s.pop());
        }
        for(int i=0;i<prerequisites.length;i++){
            int ind=-1;
            int flag=0;//cycle exists
            for(int j=0;j<order.size();j++){
                if(order.get(j)==prerequisites[i][0]){
                    ind=j+1;
                    break;
                }
            }
            for(int j=ind;j<order.size();j++){
                if(order.get(j)==prerequisites[i][1]){
                    flag=1;//no cycle
                }
            }
            if(flag==0){
                return false;
            }
        }
        return true;
    }
    public void dfs(int i,List<List<Integer>> adj,int[] visited,Stack<Integer> s){
        visited[i]=1;
        for(int item:adj.get(i)){
            if(visited[item]==0){
                dfs(item,adj,visited,s);
            }
        }
        s.add(i);
    }
}

<img width="1888" height="1062" alt="image" src="https://github.com/user-attachments/assets/d2fa9570-4c37-4f76-b8f4-2a9e52fc4a4b" />
