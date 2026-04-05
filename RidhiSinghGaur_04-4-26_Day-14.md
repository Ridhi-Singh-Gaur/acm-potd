class MinStack {
    Stack<Integer> s;
    PriorityQueue<Integer> pq;
    public MinStack() {
        s=new Stack<Integer>();
        pq=new PriorityQueue<Integer>();
    }
    
    public void push(int val) {
       s.push(val); 
       pq.add(val);
    }
    
    public void pop() {
        pq.remove(s.peek());
        s.pop();
    }
    
    public int top() {
        return s.peek();
    }
    
    public int getMin() {
        return pq.peek();
    }
}

/**
 * Your MinStack object will be instantiated and called as such:
 * MinStack obj = new MinStack();
 * obj.push(val);
 * obj.pop();
 * int param_3 = obj.top();
 * int param_4 = obj.getMin();

 */
 <img width="1918" height="1077" alt="image" src="https://github.com/user-attachments/assets/20557237-2059-4b7b-905f-e03c98af1d48" />
