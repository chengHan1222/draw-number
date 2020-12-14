# draw-number

import java.util.Scanner;

public class A410877022_11_1 {

	public static void main(String[] args) {
		Scanner scanf = new Scanner(System.in);
		String test = scanf.nextLine(); //輸入數字大小和數字 如:"2 12345"
		test = test.replaceAll("\\s+", " "); //清除輸入間過多空白
		
		while (!test.equals("0 0")) {
			int times = 0;
			String[] testInput = test.split(" ");
			int numberSize = Integer.parseInt(testInput[0]); //讀取題目給予的數字大小
			String[] number = testInput[1].split("");
			String[][] content = new String[numberSize * 2 + 3][(numberSize + 3) * number.length-1];
			//將二微陣列內部設為空白
			for (int i = 0; i < content.length; i++) {
				for (int j = 0; j < content[0].length; j++) {
					content[i][j] = " ";
				}
			}
			//將數字拆開  依依分辨是多少並畫出
			for (int i = 0; i < number.length; i++) {
				switch (number[i]) {
					case "0":
						drawZero(content, numberSize, times);
						break;
					case "1":
						drawOne(content, numberSize, times);
						break;
					case "2":
						drawTwo(content, numberSize, times);
						break;
					case "3":
						drawThree(content, numberSize, times);
						break;
					case "4":
						drawFour(content, numberSize, times);
						break;
					case "5":
						drawFive(content, numberSize, times);
						break;
					case "6":
						drawSix(content, numberSize, times);
						break;
					case "7":
						drawSeven(content, numberSize, times);
						break;
					case "8":
						drawEight(content, numberSize, times);
						break;
					case "9":
						drawNine(content, numberSize, times);
						break;
				}
				times += 1; //計算數到第幾個數字
			}
			//將二維陣列print出來
			for (int i = 0; i < content.length; i++) {
				for (int j = 0; j < content[0].length; j++) {
					System.out.print(content[i][j]);
				}
				System.out.println();
			}
			System.out.println();
			test = scanf.nextLine();
			test = test.replaceAll("\\s+", " ");
		}
		scanf.close();
	}

	// 畫出0
	static void drawZero(String[][] content, int numberSize, int number) {
		for (int j = 1; j < numberSize + 1; j++) { // 畫上橫線
			content[0][j + number * (numberSize + 3)] = "-";
			content[numberSize * 2 + 2][j + number * (numberSize + 3)] = "-";
		}
		for (int i = 1; i <= numberSize * 2 + 1; i++) { // 畫上直線
			content[i][number * (numberSize + 3)] = "|";
			content[i][(number + 1) * (numberSize + 2) + number - 1] = "|";
		}
		content[numberSize + 1][number * (numberSize + 3)] = " "; // 中間空白
		content[numberSize + 1][(number + 1) * (numberSize + 2) + number - 1] = " ";
	}

	// 畫出1
	static void drawOne(String[][] content, int numberSize, int number) {
		for (int i = 1; i <= numberSize * 2 + 1; i++) { // 畫上直線
			content[i][(number + 1) * (numberSize + 2) + number - 1] = "|";
		}
		content[numberSize + 1][(number + 1) * (numberSize + 2) + number - 1] = " "; // 中間空白
	}

	// 畫出2
	static void drawTwo(String[][] content, int numberSize, int number) {
		for (int j = 1; j < numberSize + 1; j++) { // 畫上橫線
			content[0][j + number * (numberSize + 3)] = "-";
			content[numberSize + 1][j + number * (numberSize + 3)] = "-";
			content[numberSize * 2 + 2][j + number * (numberSize + 3)] = "-";
		}
		for (int i = 1; i <= numberSize; i++) { // 畫上直線
			content[i + numberSize + 1][number * (numberSize + 3)] = "|";
			content[i][(number + 1) * (numberSize + 2) + number - 1] = "|";
		}
	}
	//畫出3
	static void drawThree(String[][] content, int numberSize, int number) {
		for (int j = 1; j < numberSize + 1; j++) { // 畫上橫線
			content[0][j + number * (numberSize + 3)] = "-";
			content[numberSize + 1][j + number * (numberSize + 3)] = "-";
			content[numberSize * 2 + 2][j + number * (numberSize + 3)] = "-";
		}
		for (int i = 1; i <= numberSize * 2 + 1; i++) { // 畫上直線
			content[i][(number + 1) * (numberSize + 2) + number - 1] = "|";
		}
		content[numberSize + 1][(number + 1) * (numberSize + 2) + number - 1] = " "; // 中間空白
	}
	//畫出4
	static void drawFour(String[][] content, int numberSize, int number) {
		for (int j = 1; j < numberSize + 1; j++) { // 畫上橫線
			content[numberSize + 1][j + number * (numberSize + 3)] = "-";
		}
		for (int i = 1; i <= numberSize; i++) { // 畫上直線
			content[i][number * (numberSize + 3)] = "|";
			content[i][(number + 1) * (numberSize + 2) + number - 1] = "|";
			content[i + numberSize + 1][(number + 1) * (numberSize + 2) + number - 1] = "|";
		}
	}
	// 畫出5
	static void drawFive(String[][] content, int numberSize, int number) {
		for (int j = 1; j < numberSize + 1; j++) { // 畫上橫線
			content[0][j + number * (numberSize + 3)] = "-";
			content[numberSize + 1][j + number * (numberSize + 3)] = "-";
			content[numberSize * 2 + 2][j + number * (numberSize + 3)] = "-";
		}
		for (int i = 1; i <= numberSize; i++) { // 畫上直線
			content[i][number * (numberSize + 3)] = "|";
			content[i + numberSize + 1][(number + 1) * (numberSize + 2) + number - 1] = "|";
		}
	}
	// 畫出6
	static void drawSix(String[][] content, int numberSize, int number) {
		for (int j = 1; j < numberSize + 1; j++) { // 畫上橫線
			content[0][j + number * (numberSize + 3)] = "-";
			content[numberSize + 1][j + number * (numberSize + 3)] = "-";
			content[numberSize * 2 + 2][j + number * (numberSize + 3)] = "-";
		}
		for (int i = 1; i <= numberSize; i++) { // 畫上直線
			content[i][number * (numberSize + 3)] = "|";
			content[i + numberSize + 1][number * (numberSize + 3)] = "|";
			content[i + numberSize + 1][(number + 1) * (numberSize + 2) + number - 1] = "|";
		}
	}
	// 畫出7
	static void drawSeven(String[][] content, int numberSize, int number) {
		for (int j = 1; j < numberSize + 1; j++) { // 畫上橫線
			content[0][j + number * (numberSize + 3)] = "-";
		}
		for (int i = 1; i <= numberSize * 2 + 1; i++) { // 畫上直線
			content[i][(number + 1) * (numberSize + 2) + number - 1] = "|";
		}
		content[numberSize + 1][(number + 1) * (numberSize + 2) + number - 1] = " "; //中間空白
	}
	// 畫出8
	static void drawEight(String[][] content, int numberSize, int number) {
		for (int j = 1; j < numberSize + 1; j++) { // 畫上橫線
			content[0][j + number * (numberSize + 3)] = "-";
			content[numberSize + 1][j + number * (numberSize + 3)] = "-";
			content[numberSize * 2 + 2][j + number * (numberSize + 3)] = "-";
		}
		for (int i = 1; i <= numberSize * 2 + 1; i++) { // 畫上直線
			content[i][number * (numberSize + 3)] = "|";
			content[i][(number + 1) * (numberSize + 2) + number - 1] = "|";
		}
		content[numberSize + 1][number * (numberSize + 3)] = " "; // 中間空白
		content[numberSize + 1][(number + 1) * (numberSize + 2) + number - 1] = " ";
	}
	// 畫出9
	static void drawNine(String[][] content, int numberSize, int number) {
		for (int j = 1; j < numberSize + 1; j++) { // 畫上橫線
			content[0][j + number * (numberSize + 3)] = "-";
			content[numberSize + 1][j + number * (numberSize + 3)] = "-";
			content[numberSize * 2 + 2][j + number * (numberSize + 3)] = "-";
		}
		for (int i = 1; i <= numberSize; i++) { // 畫上直線
			content[i][number * (numberSize + 3)] = "|";
			content[i][(number + 1) * (numberSize + 2) + number - 1] = "|";
			content[i + numberSize + 1][(number + 1) * (numberSize + 2) + number - 1] = "|";
		}
	};
}

