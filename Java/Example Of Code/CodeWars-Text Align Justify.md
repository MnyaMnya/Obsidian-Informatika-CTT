```java
import java.util.ArrayList;

public class Kata {
  public static String justify(String text, int width) {
   //Init Var
	    ArrayList<String> newLine = new ArrayList<String>();
	  int line=0;
	  String thisLine = null;
	  int spaceNeed=0;int spaceRem=0;
	  String lastLine="";
	  String tempLine="";
	  ArrayList<String> wordUsed = new ArrayList<String>();
	 //split text by space
    String [] arr = text.split(" ");
    text="";
    //loop array of split text
    for(String thisWord:arr) {
    //check if thisWord can fit in old Line
    	if((thisWord.length()+lastLine.length())+1>width) {
    	//"if" is used to prevent divided by zero error
        if(wordUsed.size()-1>0){
        // find space that needed for this line
    		spaceNeed=(width-(lastLine.length()))/(wordUsed.size()-1);
    		spaceRem=(width-(lastLine.length()))%(wordUsed.size()-1);}
    		//add the space to the line
    		for(String x:wordUsed) {
    			tempLine=tempLine+x;
    			if(x!=wordUsed.get(wordUsed.size() - 1)) {
    				for(int i=0;i<=spaceNeed;i++) {
    					tempLine=tempLine+" ";
    				}
    //add the remainder of space
    			if(spaceRem>0) {
    				tempLine=tempLine+" ";
    				spaceRem=spaceRem-1;
    			}
    		}
    		}
    	//reset some variable
    		text=text+tempLine+"\n";
    		lastLine="";
    		wordUsed.clear();
    		thisLine="";
    		tempLine="";
        spaceNeed=0;
    	}
    	// add the word to the line
    	thisLine=thisLine+thisWord;
    	wordUsed.add(thisWord);
    	//add space if thisWord is not the first in this line
    	if(lastLine !="") {
    		lastLine = lastLine+" "+thisWord;
    	}
    	else {
    	lastLine = thisWord;
    	}
    }
    text=text+lastLine;
    return text;
  }
}
```