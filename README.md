# Time-Complexities-of-Linear-Search-Vs-Binary-Search
Timing by the milliseconds for a comparison of the linear search vs the binary search algorithms.


public class TimeA
{

public static void main (String [] args){

    Long timeStart = System.currentTimeMillis();
    int[] array1 = new int[1000000];

    for(int i =0; i<array1.length-1; i++)
    {
        array1[i]=i;
    }

    int target = array1.length-20;

    int bSearch = binarySearch(array1, target);  //Binary Search Method
    System.out.println("Target found is = " + bSearch);     
    System.out.println("ANSWER OF THE Target= " + target);

    Long timeEnd = System.currentTimeMillis();

    System.out.println("Time start = " + timeStart);
    System.out.println("Time end = " + timeEnd);
    System.out.println("Time difference between start and end in Milli seconds (start - end) = " + (timeStart - timeEnd)*-1);
}


public static int binarySearch(int[] array1, int target){

    int high = array1.length-1;
    int low = 0;

    while(low <= high)
    {
        int mid = (high+low)/2;

        if(array1[mid] == target)
            return mid;
        if(target < array1[mid])
            high = mid;
        if(target > array1[mid])
            low = mid;
    }
    return 0;
  }
}
