package sample;
import java.util.Scanner;

public class MatrixAdd{
    public static int[][] read(Scanner in, int rows, int columns){
        int[][] matrix = new int[rows][columns];
        for(int i=0; i<rows; i++){
            for(int j=0; j<columns; j++){
                System.out.println("Enter value of [" + (i + 1 + "][" + (j + 1) + "]"));
                matrix[i][j] = in.nextInt();
            }
        }
        return matrix;
    }
    public static int[][] add(int[][] a, int[][] b){
        int rows = a.length;
        int columns = a[0].length;
        int[][] matrix = new int[rows][columns];
        for(int i=0; i<rows; i++){
            for(int j=0; j<columns; j++){
                matrix[i][j]=a[i][j] + b[i][j];
            }
        }
        return  matrix;
    }
    public static void printMatrix(int[][] matrix){
        int rows = matrix.length;
        int columns = matrix[0].length;
        for(int i=0; i<rows; i++){
            for(int j=0; j<columns; j++){
                System.out.println(matrix[i][j] + " ");
            }
            System.out.println();
        }
    }

   public static void main(String[] args) {
        Scanner input = new Scanner(System.in);
        System.out.println("Type number of rows : ");
        int rows = input.nextInt();
        System.out.println("Type number of columns : ");
        int columns = input.nextInt();
        System.out.println("Please type 1st matrix");
        int[][] a = read(input, rows, columns);
        System.out.println();
        System.out.println("please type 2nd matrix");
        int[][] b = read(input, rows, columns);

   int[][] sum = add(a,b);

   System.out.println("Sum of two matrices is : ");
   printMatrix(sum);

    }
}
