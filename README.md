# File-handling-Mini-project
file Existing or not,correction of word


import os
filename=input('please enter file name: ')
if os.path.isfile(filename):
    print(f'{filename} is available')
    
    option=input('read or write operation:')
    if option.lower()=='read':
        with open(filename,'r') as f:
            data=f.read()
            print(data)
        option=input('you can read more files yes|no:')
        while True:
            if option.lower()=='no':
                break
            elif option.lower()=='yes':
                break
            else:
                option=input('please enter valid option yes|no: ')
                
    elif option.lower()=='write':
        with open(filename,'w') as f:
            input_data=input('which data you inserted??')
            f.write(input_data)
        option=input('you can write more files yes|no:')
        while True:
            if option.lower()=='no':
                break
            elif option.lower()=='yes':
                break
            else:
                option=input('please enter valid option yes|no: ')
        print('data succeefully updated')
        
    elif option.lower()=='correct':
        with open(filename,'r+') as f:
            word=input('please enter old word')
            new_word=input('please enter new word')
            data=f.readlines()
            for i in data:
                if word in i:
                    replacement=i.replace(word,new_word)
                    data=replacement
            f.truncate(0)
            f.writelines(data)
            f.close()
            print('data successfully change')
    else:
        print('wrong process')
        
        
else:
    print(f'{filename} is not available')
    option=input('read more files yes|no:')
    while True:
        if option.lower()=='no':
            break
        elif option.lower()=='yes':
            break
        else:
            option=input('please enter valid option yes|no')
    print('thank you')
