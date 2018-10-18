---
UID: NF:fltkernel.FltGetLowerInstance
title: FltGetLowerInstance function
author: windows-driver-content
description: The FltGetLowerInstance routine returns an opaque instance pointer for the next lower minifilter driver instance, if there is one, that is attached below a given minifilter driver instance on the same volume.
old-location: ifsk\fltgetlowerinstance.htm
tech.root: ifsk
ms.assetid: bba47250-0344-4b5d-8461-d481519ba9ba
ms.date: 4/16/2018
ms.keywords: FltApiRef_e_to_o_6040eade-f27b-4fe5-999e-830065cafb71.xml, FltGetLowerInstance, FltGetLowerInstance routine [Installable File System Drivers], fltkernel/FltGetLowerInstance, ifsk.fltgetlowerinstance
ms.topic: function
req.header: fltkernel.h
req.include-header: Fltkernel.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: FltMgr.lib
req.dll: Fltmgr.sys
req.irql: "<= APC_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	fltmgr.sys
api_name:
-	FltGetLowerInstance
product:
- Windows
targetos: Windows
req.typenames: 
---

# FltGetLowerInstance function


## -description


The <b>FltGetLowerInstance</b> routine returns an opaque instance pointer for the next lower minifilter driver instance, if there is one, that is attached below a given minifilter driver instance on the same volume. 


## -parameters




### -param CurrentInstance [in]

Opaque instance pointer for the minifilter driver instance for which the lower minifilter driver instance is requested. 


### -param LowerInstance [out]

Pointer to a caller-allocated variable that receives an opaque minifilter driver instance pointer for the next lower minifilter driver instance. This parameter is required and cannot be <b>NULL</b>. 


## -returns



<b>FltGetLowerInstance</b> returns STATUS_SUCCESS or an appropriate NTSTATUS value, such as the following: 

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_NO_MORE_ENTRIES</b></dt>
</dl>
</td>
<td width="60%">
No lower minifilter driver instance was found. This is a warning code. 

</td>
</tr>
</table>
 




## -remarks



One instance is said to be <i>below</i> another if it is attached at a lower altitude on the same volume. The term "altitude" refers to the position that an instance occupies (or should occupy) in the minifilter driver instance stack for a volume. The higher the altitude, the farther the instance is from the base file system in the stack. Only one instance can be attached at a given altitude on a given volume. 

Altitude is specified by an <i>altitude string</i>, which is a counted Unicode string consisting of one or more decimal digits from 0 through 9, and it can include a single decimal point. For example, "100.123456" and "03333" are valid altitude strings. 

The string "03333" represents a higher altitude than "100.123456". (Leading and trailing zeros are ignored.) In other words, an instance whose altitude is "03333" is farther from the base file system than an instance whose altitude is "100.123456". However, this comparison is only meaningful if both instances are attached to the same volume. 

<b>FltGetLowerInstance</b> adds a rundown reference to the opaque instance pointer returned in the <i>LowerInstance</i> parameter. When this pointer is no longer needed, the caller must release it by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff543378">FltObjectDereference</a>. Thus every successful call to <b>FltGetLowerInstance</b> must be matched by a subsequent call to <b>FltObjectDereference</b>. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff541772">FltAttachVolume</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541775">FltAttachVolumeAtAltitude</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541889">FltCompareInstanceAltitudes</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff542995">FltGetBottomInstance</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543170">FltGetTopInstance</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543185">FltGetUpperInstance</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543378">FltObjectDereference</a>
 

 

