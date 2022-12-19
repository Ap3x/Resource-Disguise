CC_x64 		    = x86_64-w64-mingw32-g++
CC_x86 		    = i686-w64-mingw32-g++
OPTIONS		    = -lws2_32 -ldnsapi

RC_x64			= x86_64-w64-mingw32-windres
RC_x86			= i686-w64-mingw32-windres
RES_FILE	    = res/test.res 
RC_OPTIONS      = -O coff 
RC_OUTPUTFILE   = res/resource-info

OUTPUTFILE 	    = build/dns
SOURCE 		    = main.cpp 

make: clean
	@mkdir -p build

	@$(RC_x64) $(RES_FILE) $(RC_OPTIONS) -o $(RC_OUTPUTFILE)_x64.rs

	@$(CC_x64) $(SOURCE) $(RC_OUTPUTFILE)_x64.rs $(OPTIONS) -o $(OUTPUTFILE)_x64.exe
	@echo "Compiled x64 Successfully"

	@$(RC_x86) $(RES_FILE) $(RC_OPTIONS) -o $(RC_OUTPUTFILE)_x86.rs

	@$(CC_x86) $(SOURCE) $(RC_OUTPUTFILE)_x86.rs $(OPTIONS) -o $(OUTPUTFILE)_x86.exe 
	@echo "Compiled x86 Successfully"

clean:
	@rm -rf build/*.exe
	@rm -rf res/*.rs

