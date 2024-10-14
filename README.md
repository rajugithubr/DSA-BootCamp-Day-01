# DSA-BootCamp-Day-01
class Stack {
    private int[] stackArray; 
    private int top;          
    private int maxSize;      

      public Stack(int size) {
        this.maxSize = size;
        this.stackArray = new int[maxSize];
        this.top = -1;  // Stack is empty initially
    }

        public void push(int value) {
        if (isFull()) {
            System.out.println("Stack Overflow! Cannot push " + value);
        } else {
            stackArray[++top] = value; 
            System.out.println("Pushed " + value);
        }
    }

    
    public int pop() {
        if (isEmpty()) {
            System.out.println("Stack Underflow! Cannot pop");
            return -1;  
        } else {
            int poppedValue = stackArray[top--];   
            System.out.println("Popped " + poppedValue);
            return poppedValue;
        }
    }

    
    public boolean isFull() {
        return top == maxSize - 1;
    }

    public boolean isEmpty() {
        return top == -1;
    }

    
    public int peek() {
        if (isEmpty()) {
            System.out.println("Stack is empty, nothing to peek");
            return -1;
        }
        return stackArray[top];
    }

    
    public int size() {
        return top + 1;
    }

    public static void main(String[] args) {
        
        Stack stack = new Stack(5);

        
        stack.push(10);
        stack.push(20);
        stack.push(30);

        
        stack.pop();
        stack.pop();

        
        System.out.println("Top element is: " + stack.peek());

        
        stack.push(40);
        stack.push(50);
        stack.push(60);

      
        stack.push(70); 
    }
}
