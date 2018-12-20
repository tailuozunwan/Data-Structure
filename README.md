# Data-Structure
#include <iostream>
#include <cstdlib>
#include <iomanip>
using namespace std;
int A[2][3]={{1,2,3},{4,5,6}};
int B[3][3]={{1,0,1},{1,1,0},{0,1,0}};
int C[2][3];
class fun{
	public:
	  void matrix_one(int m,int n);
	  void matrix_two(int m,int n);
	  void matrix_thr(int m,int n);
	void matrix_mul(int m,int n);
};


int main()
{
	fun obj;
	//obj.matrix_one(4,4);
	//obj.matrix_two(4,4);
	//obj.matrix_thr(4,4);
	obj.matrix_mul(2,3);
	return 0;
}

void fun::matrix_one(int m, int n)
{
  cout<<"not transform:"<<"\n";
  int i,j;
	for(i=0;i<m;i++){
	for(j=0;j<n;j++)
	cout<<	setw(4)<<A[i][j];
	cout<<"\n";
		}
}


void fun::matrix_two(int m,int n){
	int i,j;
	for(i=0;i<m;i++)
	for(j=0;j<n;j++)
	B[j][i]=A[i][j];

}

void fun::matrix_thr(int m, int n)
{
  cout<<"transform:"<<"\n";
  int i,j;
	for(i=0;i<m;i++){
	for(j=0;j<n;j++)
	cout<<	setw(4)<<B[i][j];
	cout<<"\n";
		}
}
void fun::matrix_mul(int m, int n){
	int i,j,k;
	for(i=0;i<m;i++)
	for(j=0;j<n;j++){
	C[i][j]=0;
   for(k=0;k<n;k++)
	C[i][j]= A[i][k]*B[k][j]+C[i][j];
	}
	
	for(i=0;i<m;i++)
	for(j=0;j<n;j++)
	cout<<setw(3)<<C[i][j];
	cout<<"\n";
}
