# Use Intention-Revealing Names

>Coosing names takes time but saves more than takes.

Its easy to say that names should reveal intent. 

The name of variable, function or clas should answer all the big questions. It should tell you why its exists, what its does, and how it used. If a name requires comment than the name does not reveal its intent.

for example ; 

    int d; // elapsed time in days

    int elapsedTimeInDays;

    
What the purpose of this code ;
    
    public List<int[]> getThem() {
        List<int[]> list1 = new ArrayList<int[]>();
        for (int[] x : theList)
            if (x[0] == 4)
            list1.add(x);
            return list1;
    }    

hard to tell.

    public List<int[]> getFlaggedCells() {
        List<int[]> flaggedCells = new ArrayList<int[]>();
        for (int[] cell : gameBoard)
            if (cell[STATUS_VALUE] == FLAGGED)
                flaggedCells.add(cell);
        return flaggedCells;
    }
Notice that the simplicity of the code has not changed.  But the code
has become much more explicit.