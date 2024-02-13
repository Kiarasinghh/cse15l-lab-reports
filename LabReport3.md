## Part 1

# Bugged Program:

Before:
``
  static int[] reversed(int[] arr) {
    int[] newArray = new int[arr.length];
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = newArray[arr.length - i - 1];
    }
    return arr;
  }
``
After: 
``
  static void reverseInPlace(int[] arr) {
    for(int i = 0; i < arr.length/2; i += 1) {
      int temp = arr[i];
      arr[i] = arr[arr.length - i - 1];
      arr[arr.length-i-1]=temp;
    }
  }
``
The bug was that by the time we got to the last element, changing it to the first one meant not actually changing it’s value. This is because the first element = last element. By only going up to half the length of the array, this issue is avoided as once we get to the middle, all the elements have already been reversed. When there is a odd number of elements in the lis, the element in the middle index wouldn't change in this code, which works with what the function is trying to do. 

# Faliure inducing input:
``
@Test 
public void testReverseInPlace() {
  int[] input1 = {3,4,5};
  ArrayExamples.reverseInPlace(input1);
  assertArrayEquals(new int[]{5,4,3}, input1);
	}
``
The output for the above code should have been 5,4,3 but it ws 5,4,5

![Image](345.png) 


# Succesfull input:
``
	@Test 
	public void testReverseInPlace() {
    int[] input1 = {3,3};
    ArrayExamples.reverseInPlace(input1);
    assertArrayEquals(new int[]{3,3}, input1);
	}
 ``
 ![Image](3,3.png) 

## Part 2 

Chosen command: find 

# Option 1: 


