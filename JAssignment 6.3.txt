class bank
{
	public synchronized void deposit() throws InterruptedException
	{
		System.out.println("you are depositing the amount");
		Thread.sleep(5000);
		System.out.println("deposit completed");
	}
	public synchronized void withdraw() throws InterruptedException
	{
		System.out.println("you are withdrawing the amount");
		Thread.sleep(5000);
		System.out.println("withdraw completed");
	}
}
class bankPerform extends Thread
{
	public void run()
	{
		try {
			BankSynchronized.bf.deposit();
			BankSynchronized.bf.withdraw();
		} catch (InterruptedException e) {
			// TODO Auto-generated catch block
			e.printStackTrace();
		}
		
	}
}
class bankPerform2 extends Thread
{
	public void run()
	{
		try {
			BankSynchronized.bf.deposit();
			BankSynchronized.bf.withdraw();
		} catch (InterruptedException e) {
			// TODO Auto-generated catch block
			e.printStackTrace();
		}
		
	}
}

public class BankSynchronized {

	public static bank bf;
	public static void main(String[] args) {
		// TODO Auto-generated method stub
		bf=new bank();
		bankPerform bp=new bankPerform();
		bankPerform2 bp2=new bankPerform2();
		bp.start();
		bp2.start();
	}

}
