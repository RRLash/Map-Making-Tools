I believe that using python can help automate repetitive tasks in ArcGIS, but actually getting the code to run can be *very frustrating*!  Here's a collection of some code/scripts I've used.

##Field Calculator
I always seem to have a difficult time performing Attribute Field Calculations.  Here's a few tips:
1. The order of operations is controlled by spacing: start loops with 2-spaces, and lines within looms with 4-spaces  

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
