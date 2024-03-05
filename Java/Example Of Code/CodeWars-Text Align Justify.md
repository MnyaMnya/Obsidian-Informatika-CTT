```java
import java.util.ArrayList;

public class Kata {
  public static String justify(String text, int width) {
	    ArrayList<String> newLine = new ArrayList<String>();
	  int line=0;
	  String thisLine = null;
	  int spaceNeed=0;int spaceRem=0;
	  String lastLine="";
	  String tempLine="";
	  ArrayList<String> wordUsed = new ArrayList<String>();
    String [] arr = text.split(" ");
    text="";
    for(String thisWord:arr) {
    	if((thisWord.length()+lastLine.length())+1>width) {
        if(wordUsed.size()-1>0){
    		spaceNeed=(width-(lastLine.length()))/(wordUsed.size()-1);
    		spaceRem=(width-(lastLine.length()))%(wordUsed.size()-1);}
    		for(String x:wordUsed) {
    			tempLine=tempLine+x;
    			if(x!=wordUsed.get(wordUsed.size() - 1)) {
    				for(int i=0;i<=spaceNeed;i++) {
    					tempLine=tempLine+" ";
    				}
    			if(spaceRem>0) {
    				tempLine=tempLine+" ";
    				spaceRem=spaceRem-1;
    			}
    		}
    		}
    		text=text+tempLine+"\n";
    		lastLine="";
    		wordUsed.clear();
    		thisLine="";
    		tempLine="";
        spaceNeed=0;
    	}
    	thisLine=thisLine+thisWord;
    	wordUsed.add(thisWord);
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