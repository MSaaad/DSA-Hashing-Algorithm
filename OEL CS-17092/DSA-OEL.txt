
# ------------------------------------- Main Hash Table [Phone Directory] ---------------------------------------- #

hashtable = {0 : [None],1:[None],2:[None],3:[None] , 4:[None],5:[None],
             6:[None],7:[None],8:[None],9:[None],10:[None],11:[None],12:[None],
             13:[None],14:[None],15:[None],16:[None],17:[None],18:[None],19:[None],
             20:[None],21:[None],22:[None],23:[None],24:[None],
             25:[None],26:[None],27:[None],28:[None],29:[None],
             30:[None],31:[None],32:[None],33:[None],
             34:[None],35:[None],36:[None],37:[None],38:[None],
             39:[None],40:[None],41:[None],42:[None],43:[None],44:[None],
             45:[None],46:[None],47:[None],48:[None],
             49:[None],50:[None],51:[None],
             52:[None],53:[None],54:[None],55:[None],56:[None],57:[None],
             58:[None],59:[None],
             60:[None],61:[None],62:[None],63:[None],64:[None],65:[None],
             66:[None],67:[None],68:[None],69:[None],
             70:[None],71:[None],72:[None],73:[None],74:[None]}

# ------------- Printing Hash Table ----------- #

print(hashtable)

# -------- Taking User Input Five Times ------------- #

for _ in range(30):
  print('\n')
  employee_name = input('Enter the employee name:')
  landline = int(input('Enter the telephone number:'))
  mobile = int(input('Enter the mobile number:'))
  employee_number = int(input('Enter the employee number:'))  

# --------- Length of Employee Number less than Five -------- #

  if len(str(employee_number)) < 6:

# -------- hashing Function ---------- #

    hashing = employee_number % 73
    counter = 1
    while hashtable[hashing] != [None]:                #When the key is not None[Empty Slot]
      if hashing == 72:
        hashing = -1
      counter = counter + 1                                       #Incrementing Counter Variable
      hashing = hashing + 1                                        #Incrementing hashing Value 
    hashtable[hashing] = [employee_number , employee_name , mobile , landline]      #Placing  hashed key value in the main hash table   
    print('\n',counter, 'Probe(s)','\n')
    print(hashtable)                 # Printing Main Hash Table
  else:
    print('Please Enter a five digit number!' )                 #If user entered greater than five digit employee number, loop will break
    break

# ------------ Searching Function ---------- #

def search(): 
    employee_number = int(input('Enter the employee number you want to search: '))
    counter=1                                                                                                              
    hashing = employee_number % 73
    found = False
    while hashtable[hashing] != [None]:               #When the slot is not empty
      if employee_number == hashtable[hashing][0]:          #When employee number matches the zeroth index of the hashed key of the hash table
        found = True
        break
      hashing += 1                            #Incrementing Hashing key
      counter += 1                            #Incrementing Counter Variable
      print('Probe(s)' , counter)                    #Print the value of counter inside the loop
      print(hashtable[hashing])          #Gathering the value of the hashed key from the main hash table
    if found:
      print('\t Successful Search \n \t Number of Probe(s)' , counter)        #Print Successful searching Probing Value
      print(hashtable[hashing])
    else:
      print('\t  Unsuccessful Search \n \t Number of Probe(s)' , counter)      #Print Uncsuccessful searching Probing Value
    
