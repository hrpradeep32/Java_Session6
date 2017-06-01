class primeOrNot
{
	public boolean primeCheck(int num)
	{
		int half=num/2;
		int i=2;
		for(int k=0;i<=half;i++)
		{
			if(num%i==0)
				return false;
		}
		if(i>half)
			return true;
		return true;
	}
}
class primeThread extends Thread
{
	public void run()
	{
		primeOrNot pon=new primeOrNot();
		boolean result=pon.primeCheck(31);
		if(result==true)
		{
			System.out.println("the given number is prime");
		}
		else if(result==false)
		{
			System.out.println("the given number is not prime");
		}
	}
}
public class PrimeUsingThread {

	public static void main(String[] args) {
		// TODO Auto-generated method stub
		primeThread pt=new primeThread();
		pt.start();
	}

}
