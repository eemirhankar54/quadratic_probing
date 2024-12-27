# quadratic_probing

#include <stdio.h>

int arr[7]; 

void print()
{
	printf("\n existing elements of the array");
	for(int i=0;i<7;i++)
	{
		printf("\n %d.index ==> %d",i,arr[i]);
	}
}


int hash(int search)
{
	int mod = search % 7;
	return mod;
}



void insert(int add)
{
	int index = hash(add);
	if(arr[index] == 0)
	{
		arr[index] = add;
	}
	else
	{
		for(int i = 0;i < 7;i++)
		{
			int control = (index + i*i) % 7;
			if(arr[control] == 0)
			{
				arr[control] = add;
				return;	
			}	
		}
  	printf("Array is full or collision cannot be resolved.\n");
	}
	

}



int main()
{
	insert(21);
	insert(22);
	insert(23);
	insert(23);
	insert(25);
	insert(26);
	insert(27);
	insert(29);
	print();
	return 0;
}
