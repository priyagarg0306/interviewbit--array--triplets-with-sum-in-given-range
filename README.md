# interviewbit--array--triplets-with-sum-in-given-range

**-------> Question:**

Given an array of real numbers greater than zero in form of strings.

Find if there exists a triplet (a,b,c) such that 1 < a+b+c < 2 . 

 Return 1 for true or 0 for false.

Example:

Given [0.6, 0.7, 0.8, 1.2, 0.4] ,

You should return 1

as

0.6+0.7+0.4=1.7

1<1.7<2

Hence, the output is 1.

O(n) solution is expected.

Note: You can assume the numbers in strings don’t overflow the primitive data type and there are no leading zeroes in numbers. Extra memory usage is allowed.


**-------> perfect code in O(n):**

int Solution::solve(vector<string> &v) {

   int n=v.size();
    vector<double> v1;
    for(int i=0;i<n;i++){
        v1.push_back(stod(v[i]));
    }

    sort(v1.begin(),v1.end());
    
    double sum;
    int x=0,y=n-1;
    
        while(y-x>=2){
            int mid=(x+y)/2;
            sum=v1[mid]+v1[x]+v1[y];
            if(sum>1.0 && sum<2.0){
                return 1;
            }else if(sum>2.0){
                y--;
            }else{
                x++;
            }
        }
    
    return 0;
}
