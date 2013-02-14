
/**
 * This class is meant to create the board for the checkers to be placed on.
 * This is done using a 2-d array that holds the rows and columns. The class
 * does this by looping through both dimensions of the array. In order to tell which 
 * color the square needs to be, black or red, is determined by adding the values
 * of the row and column. For example, if its in the 3rd row, 2nd column, the values 
 * in Java of rows/columns are 2, 1. 2+1=3, and since the value there is odd, the
 * color will be black. 
 * 
 * @author Lily Dam and Ryan Finney
 * @version February 14, 2013
 */
//imports 
import objectdraw.*;
import java.awt.*;

public class CheckerBoard
{   
    //2D array to hold rows/columns of boxes
    private FilledRect[][] boxes;
   
    //starting values to place boxes
    private int startX=5, startY=5;
    
    //sets the size of each box and top/left of the board
    public static final int SIZE=30, TOP=5, LEFT=5;
    
    //canvas to use in order for the Checker class to be compatible
    public DrawingCanvas canvas;
    
    //constructor for the board, creates the squares and places them in their correct spots
    public CheckerBoard(int row, int col, DrawingCanvas canvas)
    {
        //initializes the 2D array
        boxes= new FilledRect[row][col];
        //gets the amount of rows and columns in board
        int rows=boxes.length, cols=boxes[0].length;  
        
        //looping structure to create the rows of the board
        for(int r=0; r<rows; r++)
        {
            //internal looping structure to create the columns in each row
            for(int c=0; c<cols; c++)
            {
                //creates a box at the current values
                boxes[r][c]= new FilledRect(startX,startY,SIZE,SIZE,canvas);
                //incriments startX to create the next box
                startX+=SIZE;
                
                //conditional statement used to check if the box should be red or not
                if((r+c)%2==0)
                    boxes[r][c].setColor(Color.red);
            }
            //incriments the startY to change the y value where the boxes are created
            startY+=SIZE;
            
            //resets the value of startX 
            startX=LEFT;
        }
        //initializes the canvas
        this.canvas=canvas;
    }
    
    //method to change the colors of the squares
    public void changeColor(Color color1, Color color2)
    {
        //gets the rows and columns of the board
        int rows=boxes.length, cols=boxes[0].length;
          //gets the current colors
        Color CurrentColor1=boxes[0][0].getColor();
        Color CurrentColor2= boxes[0][1].getColor();
        //same looping structure as above
        for(int r=0; r<rows;r++)
        {
            for(int c=0; c<cols; c++)
            {
                //changes the colors of the boxes
                if(boxes[r][c].getColor()==CurrentColor1)
                    boxes[r][c].setColor(color1);
                else if(boxes[r][c].getColor()==CurrentColor2)
                    boxes[r][c].setColor(color2);
            }
        }
    }
    
    //method used to get the number of rows in the box
    public int getRows()
    {
        int rows= boxes.length;
        return rows;
    }
    
    //method used to get the number of columns in the box
    public int getCols()
    {
        int cols=boxes[0].length;
        return cols;
    }
    
    //method used to get the color of the box at the location passed in
    public Color getBoxColor(int row, int col)
    {
        Color boxColor= boxes[row][col].getColor();    
        return boxColor;
    }
}
