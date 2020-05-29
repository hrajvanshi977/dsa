package A;
public class Solution {
		static int[] heap;
		static int size;
		 static int maxsize;
		private static int FRONT = 1;
		
		Solution(int maxsize){
			this.maxsize = maxsize;
			this.size = 0;
			heap = new int[maxsize+1];
			heap[0] = Integer.MIN_VALUE;
		}
		static int parent(int position) {
			return position/2;
		}
		static void swap(int current, int parent) {
			int temp = heap[current];
			heap[current] = heap[parent];
			heap[parent] = temp;
		}
		static void print() {
			for(int i=1;i<=size/2;i++) {
				System.out.print("PARENT : ");
				System.out.print(heap[i]+" ");
				System.out.print("LEFT CHILD : "+heap[2*i]+" : "+"RIGHT CHILD : "+heap[2*i+1]);
				System.out.println();
			};
			
		}
		static boolean isLeaf(int position) {
			return position > size/2 && position <= size;
		}
		static int leftChild(int position) {
			return 2*position;
		}
		static int rightChild(int position) {
			return 2*position + 1;
		}
		static void minHeapify(int position) {
			
			if(isLeaf(position)) {
				if(heap[position]  > heap[leftChild(position)] || heap[position] > heap[rightChild(position)]) {
					
					if(heap[leftChild(position)] < heap[rightChild(position)]) {
						swap(position, leftChild(position));
						minHeapify(leftChild(position));
					}
					else {
						swap(position, rightChild(position));
						minHeapify(rightChild(position));
					}
				}
			}
		}
		static void minHeap() {
			for(int position = size/2; position >= 1;position--) {
				minHeapify(position);
			}
		}
	static void insert(int element) {
		if(size >= maxsize) {
			return; 
		}
		heap[++size] = element;
		int current = size;
		
		while(heap[current] < heap[parent(current)]) {
			swap(current, parent(current));
			current = parent(current);
		}
	}
	static int remove() {
		int popped = heap[FRONT];
		heap[FRONT] = heap[size--];
		minHeapify(FRONT);
		return popped;
	}
	public static void main(String args[]) {
		
		Solution mn = new Solution(15);
		
		insert(1);
		insert(10);
		insert(45);
		insert(25);
		insert(4);
		insert(17);
		insert(6);
		insert(11);
		
		minHeap();
		//remove();
		print();
	
	}
}
