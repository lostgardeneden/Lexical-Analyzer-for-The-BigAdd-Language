# Lexical-Analyzer-for-The-BigAdd-Language

#Analysis

This project requests a lexical analyzer for BigAdd Language. The lexical analyzer must take input from a user to use the filename. The input file will read from the code and the lexical analyzer will analyze its demands.  For understanding “BigAdd Language”, the code must have known what this language looks like. The lexical analyzer should recognize the keywords, identifiers, constants, end of line symbols, etc. If the lexical analyzer encounters an error, it should print an error message on the screen. Also, the lexical analyzer must write what reads on the file to a new file that has the same name but a different extension.
BigAdd language is a language that consists only of int-type data. This language includes assignment, addition, subtraction, loops, code blocks and comments. In addition, there are string constants written within the characters “ “ in the language.


#Design

We tried to design this project with the most efficient way. Firstly, we take the name of the file that the user wants to read as input. The code opens the file by adding an extension to this input value. Then, it writes what it reads from the BigAdd language code to a file with the same file name but a different extension. To analyze the code in the file, the text read is split into lines. Then, each line is checked with the "containPar" method to see if it contains a comment line. If there is a comment line, it is deleted. After this process, if there is an end of line symbol in the code, this symbol is also deleted from the line with the “strEndsWith” method. If there is not an end of line symbol, the error output is printed on the screen.
The remaining line of code is sent to the "analyze" method for analysis. In the "analyze" method, lines are split into words. Then each split word is classified, the code is analyzed. We have created methods such as "isKeyword", "isInt", "isIntVariable", "isVariable" to classify words. In these methods, we made the definitions in accordance with the BigAdd language.

If there is an error or deficiency in the code read, this error is printed on the screen as output.
Part of the code does not work because previously defined integer variables in the "analyze" method cannot be found in the "variables" list.  "loop" and "move" parts do not work because we could not solve this problem. 
Also, we could not write the analysis results into the "newFile" that file we created.  We tried to use fprintf, fputs and fputc methods, but they did not work. We realized that these methods worked when we changed the file extension to "txt".  However, we did not delete the lines written into the file so that there is no deficiency in the code. We could not write the results to the file, so we printed them as output to the screen.
