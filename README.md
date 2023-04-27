# ImplementsThread
package com;

public class MyRunnableThread implements Runnable{
	public static int mycount=0;
	public MyRunnableThread() {
		
	}
      public void run() {
    	  while(MyRunnableThread.mycount<=10) {
    		  try {
    			  System.out.println("Expl Thread:"+(++MyRunnableThread.mycount));
    			  Thread.sleep(0);
    		  } 
    		  catch(InterruptedException iex) {
    			  System.out.println("Exception in Thread:"+iex.getMessage());
    			  
    		  }
    	  }
      }
	public static void main(String[] args) {
		// TODO Auto-generated method stub
		System.out.println("Starting main thread....");
		MyRunnableThread mtr=new MyRunnableThread();
		Thread t=new Thread(mtr);
		t.start();
		while(MyRunnableThread.mycount<=10) {
			try {
  			  System.out.println("Expl Thread:"+(++MyRunnableThread.mycount));
  			  Thread.sleep(0);
  		  } 
  		  catch(InterruptedException iex) {
  			  System.out.println("Exception in Thread:"+iex.getMessage());
  			  
  		  }
		}

	}

}
