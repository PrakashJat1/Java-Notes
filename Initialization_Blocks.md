										#INITIALIZATION BLOCK

-> In the above example we are writing count++ (for counting the number of object creations) in all the constructors to avoid this repetition initialization can be used.
-> Types:-
		1). Instance Initialization Block -  (i) For every object creation, an Instance Initialization block will be called.
                                                    (ii) This block will be called before the constructor.
						   (iii) we can have more than one instance Initialization Block in that case they will be executed from top to bottom.
						     
		
		2)Static Initialization Block - (i) Whenever the class is loaded in memory then Static Initialization Block will be executed.
						(ii) Whenever we call any executable block then the class is loaded in memory.
						(iii) Class will be loaded in memory only at once.