# RhinoRenameObjectsByLayerName
Rhinoceros - Rename selected objects by their layer's name


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
    
    
