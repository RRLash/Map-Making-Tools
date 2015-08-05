Using python can help automate repetitive tasks in ArcGIS, but  getting the code to run can sometimes be *very frustrating*!  Here's a collection of some code/scripts I've used.

##Field Calculator
I always seem to have a difficult time performing Attribute Field Calculations.  Here's a few tips:  
1. The order of operations is controlled by spacing: start loops with 2-spaces, and lines within loops with 4-spaces  

###Example converting variable type text numerals to float
This script copies numbers stored as a string variable, and converts them to a floating point variable, while converting any null values to '-99.'  This syntax only works for ArcGIS versions 10.1 and newer, and I took it from [this ESRI page](http://support.esri.com/en/knowledgebase/techarticles/detail/41414).

Pre-Logic Script Code:
```
#Define a python function using the syntax 'def <FunctionName>(InputField):'
def update(value):

  #Create a return value variable, and set its value to '-99'
  retValue = -99
  
  #If the Input Value is NOT Null (Python uses the term 'None' for null values), 
  #then convert the Input Value to a Floating type variable, and set it as the return value
  if value is not None:
    retValue = float(value)
  
  #Pass the return value on to the Output Field
  return retValue
```
[OutputFieldName] =
```
#Run the above define update function ong the Input Field
update( !InputFieldName!)
```
###Example reclassifying numerial data with If...Then statement
I made this script when I was playing with some data on the distribution of Starbucks in various states.  It reclassifies "NULL" values (aka "None" in python syntax) to 1, and leaves existing 0 values as 0 

Pre-Logic Script Code:
```
def Reclass(Starbucks):

  if Starbucks is None:
    return 1

  if Starbucks == 0:
    return 0
```
[OutputFieldName] =
```
Reclass( !Starbucks! )
```
###Example setting values in a new field based on values in an exisiting fields
Continuing with the data from above, I wanted to populate a new text field called "Recommend" based on its proximity to exisitng Starbuck locations.  The proximity to a Starbucks is already coded in the "Starbucks" field, and for each value in this field I wanted a corresponding recommendation in the "Recommend" field.

Pre-Logic Script Code:
```
def Update(Starbucks, Recommend):

  if Starbucks == 0:
     Recommend =  "Be ready to make your own cappuccino"
     return Recommend

  if Starbucks == 1:
    Recommend = "You can find a Starbucks, but you will have to drive"
    return Recommend
 
  if Starbucks == 2:
    Recommend = "You can easily find Starbucks coffee"
    return Recommend
```
[OutputFieldName] =
```
Update( !Starbucks!, !Recommend! )
```
