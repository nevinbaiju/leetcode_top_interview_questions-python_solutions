# [Valid Sudoku](https://leetcode.com/explore/interview/card/top-interview-questions-easy/92/array/769/)

The solution checks rows, columns and squares seperately and checks if any numbers are repeated using a hash map.
Since the size of the input is fixed, the solution runs on constant runtime.
___
```
class Solution:
    
    def notValid(self, numbers):
        hash_map = {}
        for number in numbers:
            try:
                if ((hash_map[number]) & (number != ".")):
                    return True
            except KeyError:
                hash_map[number] = True
        return False
    
    def isValidSudoku(self, board):
        # Validating rows
        for row in board:
            if (self.notValid(row)):
                return False
        # Validating columns
        for column in range(9):
            col_vals = [row[column] for row in board]
            if (self.notValid(col_vals)):
                return False
        # Validating squares
        for row_id in range(0, 3):
            for col_id in range(0, 3):
                square_vals = []
                sq_rows = [board[row_id*3 + x][col_id*3:(col_id+1)*3] for x in range(3)]
                square_vals = sq_rows[0] + sq_rows[1] + sq_rows[2]
                if (self.notValid(square_vals)):
                    return False
        
        return True
```
___