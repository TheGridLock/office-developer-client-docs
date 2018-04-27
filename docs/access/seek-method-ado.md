---
title: "Seek Method (ADO)"
 
 
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
  
localization_priority: Normal
ms.assetid: cf0f133b-31f2-a2df-6cf3-1b5fa73b516c

---

# Seek Method (ADO)

Searches the index of a [Recordset](recordset-object-ado.md) to quickly locate the row that matches the specified values, and changes the current row position to that row. 
  
## Syntax

 *recordset*  . **Seek** *KeyValues*  ,  *SeekOption* 
  
## Parameters

-  *KeyValues* 
    
- An array of **Variant** values. An index consists of one or more columns and the array contains a value to compare against each corresponding column. 
    
-  *SeekOption* 
    
- A [SeekEnum](seekenum.md) value that specifies the type of comparison to be made between the columns of the index and the corresponding  *KeyValues*  . 
    
## Remarks

Use the **Seek** method in conjunction with the [Index](index-property-ado.md) property if the underlying provider supports indexes on the **Recordset** object. Use the [Supports](supports-method-ado.md) **(adSeek)** method to determine whether the underlying provider supports **Seek**, and the **Supports(adIndex)** method to determine whether the provider supports indexes. (For example, the [OLE DB Provider for Microsoft Jet](microsoft-ole-db-provider-for-microsoft-jet.md) supports **Seek** and **Index**.) 
  
If **Seek** does not find the desired row, no error occurs, and the row is positioned at the end of the **Recordset**. Set the **Index** property to the desired index before executing this method. 
  
This method is supported only with server-side cursors. Seek is not supported when the **Recordset** object's [CursorLocation](cursorlocation-property-ado.md) property value is **adUseClient**. 
  
This method can only be used when the **Recordset** object has been opened with a [CommandTypeEnum](commandtypeenum.md) value of **adCmdTableDirect**. 
  
