# Data-Structure
package dynamicArray;

class Array{
	int[] arr;
	int len=0;
	int capacity=0;
	Array(){
		this(16);
		
	}
	Array(int capacity){
		this.capacity=capacity;
		arr=new int[capacity];
	}
	//add method to add element
	public void add(int data) {
		if(len+1>=capacity) {
			int i=0;
			int[] new_array;
			if(capacity==0) {
				capacity=1;
			}else {
				capacity*=2;
			}
			new_array=new int[capacity];
			
			for(i=0;i<len;i++) {
				new_array[i]=arr[i];
			}
			arr=new_array;
			
		}
		arr[len++]=data;
		
	}
	//remove element at array
	public int removeAt(int index) {
		System.out.println("in remove "+capacity);
		int data=0;
		if(index<0 && index>len) {
			System.out.println("out of index");
		}
		data=arr[index];
		int[] new_array=new int[len-1];
		int i=0,j=0;
		for(i=0,j=0;i<len;i++,j++) {
			if(i==index) {
				j--;	
			}else {
				new_array[j]=arr[i];	
			}
		}
		arr=new_array;
		
		capacity=--len;
		return data;	
		
	}
	//length of array
	public int len() {
		return len;
	} 
	//capacity of array
	public int capacity() {
		return capacity;
	}
	//at the index of 
	public int indexOf(int index) {
		return arr[index];
	}
	//element is present or not
	public boolean contains(int obj) {
		int i=0; 
		for(i=0;i<len;i++) {
			if(obj==arr[i]) {
				return true;
			}
		}
		return false;
	}
	//this print all element of array 
	public void printAll() {
		for(int i=0;i<len;i++) {
			System.out.print(arr[i]+" ");
		}
	}
}
public class DynamicArray {

	public static void main(String[] args) {
		// TODO Auto-generated method stub
		Array a=new Array(0);
		//this add element to array
		a.add(10);
		a.add(20);
		a.add(30);
		a.add(40);
		//print all array element
		a.printAll();
		//remove element at given index
		a.removeAt(2);
		//this print length of array
		System.out.println(a.len());
		//this print true if element present in array otherwise false 
		System.out.println(a.contains(40));
		//this print array element
		a.printAll();
		//element at given index
		System.out.println(a.indexOf(2));
		
		

	}

}
