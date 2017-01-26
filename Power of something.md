# Power of Two
## Naive solution:
     public boolean isPowerOfTwo(int n) {
        if(n==0)
            return false;
        if(n==1)
            return true;
        while(n!=1){
            if(n%2!=0)
                return false;
            n=n/2;
        }
        return true;
    }
## Better solution with n&(n-1) trick:
    public boolean isPowerOfTwo(int n) {
        if(n<=0)
            return false;
        if((n&(n-1))==0)
            return true;
        return false;
    }

# Power of Three
## Using max Int value:
    public boolean isPowerOfThree(int n) {
        if(n<=0)
            return false;
        int max = (int)Math.pow(3,(int)(Math.log10(0x7fffffff)/Math.log10(3)));
        if(max%n==0)
            return true;
        return false;

    }
    
## Have to use log of base 10:
     public boolean isPowerOfThree(int n) {
        if(n==0)
            return false;
        if(Math.log10(n)/Math.log10(3)%1==0)
            return true;
        else
            return false;
    }
