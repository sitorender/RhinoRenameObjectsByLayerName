# RhinoRenameObjectsByLayerName
Rhinoceros - Rename selected objects by their layer's name
fond here: https://discourse.mcneel.com/t/renaming-objects-by-layer/33668/2


Rename by Layer::sublayer

import rhinoscriptsyntax as rs  
objList = rs.GetObjects("Select objects to name") 
for obj in objList:     
    layer = rs.ObjectLayer(obj)     
    layerName = rs.LayerName(layer)     
    rs.ObjectName(obj, layerName)   
    
    
Rename by sublayer only

import rhinoscriptsyntax as rs  
objList = rs.GetObjects("Select objects to name")   
for obj in objList:   
    layer = rs.ObjectLayer(obj)   
    layerName = rs.LayerName(layer, False)  
    rs.ObjectName(obj, layerName)   
    
    
Run the script (tools>pythonscript>edit)
copy/paste/selectthecode/play
select the object to rename
enter

You can create a button with the code: hold ctrl and duplicate a single button on a toolbar
hold shift and right click on the new button delete the current script and replace it with this (sublayer)

! _-RunPythonScript (
import rhinoscriptsyntax as rs  
objList = rs.GetObjects("Select objects to name")   
for obj in objList:   
    layer = rs.ObjectLayer(obj)   
    layerName = rs.LayerName(layer, False)  
    rs.ObjectName(obj, layerName)  
)

and this for the right click (layer::sublayer)

! _-RunPythonScript (
import rhinoscriptsyntax as rs  
objList = rs.GetObjects("Select objects to name") 
for obj in objList:     
    layer = rs.ObjectLayer(obj)     
    layerName = rs.LayerName(layer)     
    rs.ObjectName(obj, layerName)   
)

edit the button icon image (in the up right corner)

