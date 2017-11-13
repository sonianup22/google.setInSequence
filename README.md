# google.setInSequence

//	input = {-1,0,1,2,4,5,8}
//	Output = {  -1->2,
                4->5,
                8} 


package gov.dol.bls.dbes.quest;

public class main {
    public static void main(String []args){
       
    	System.out.println("Hello World");
       
       int[] inputArray = new int[]{-1,0,1,2,4,5,8,9};
       main m = new main();
       String[] name = m.process_seq(inputArray);
       for(String n  : name){
    	   if(n != null){
	    	   System.out.print( n );
	    	   System.out.print(",");
    	   }
       }

    }
    
    public String[] process_seq(int[] input){
    	int len = input.length;
        String[] result = new String[len];
        int j =0;
        int swapInt = 0;
        int start = 0;
        
        for(int i=0; i<=len;i++){
            
           if(i == 0){
        	   start = swapInt = input[0];
           } else{
               if(i==len){
            	   result[j] = Integer.toString(start);
               }
               else if(swapInt + 1 == input[i]){
                   swapInt = input[i];
               }
               else{
            	    result[j] = start + "->" + swapInt;
            	    swapInt = input[i];
            	    start = swapInt;
                    j++;
               }
           }   
            
        }
        
        return result;
    }
}
