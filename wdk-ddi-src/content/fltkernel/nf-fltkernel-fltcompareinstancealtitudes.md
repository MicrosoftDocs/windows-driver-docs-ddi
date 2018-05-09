---
UID: NF:fltkernel.FltCompareInstanceAltitudes
title: FltCompareInstanceAltitudes function
author: windows-driver-content
description: FltCompareInstanceAltitudes compares the altitudes of two minifilter driver instances.
old-location: ifsk\fltcompareinstancealtitudes.htm
old-project: ifsk
ms.assetid: aed86b34-4a9e-4c39-be0f-fa57829fa926
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: FltApiRef_a_to_d_5f6cccb8-671c-495a-9c18-c262d4845105.xml, FltCompareInstanceAltitudes, FltCompareInstanceAltitudes function [Installable File System Drivers], fltkernel/FltCompareInstanceAltitudes, ifsk.fltcompareinstancealtitudes
ms.prod: windows-hardware
ms.technology: windows-devices
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
req.dll: 
req.irql: "<= DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	FltMgr.lib
-	FltMgr.dll
api_name:
-	FltCompareInstanceAltitudes
product:
- Windows
targetos: Windows
req.typenames: 
---

# FltCompareInstanceAltitudes function


## -description


<b>FltCompareInstanceAltitudes</b> compares the altitudes of two minifilter driver instances. 


## -parameters




### -param Instance1 [in]

Pointer to the first instance. 


### -param Instance2 [in]

Pointer to the second instance. 


## -returns



<b>FltCompareInstanceAltitudes</b> returns a signed value that gives the results of the comparison as follows: 

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>Zero</b></dt>
</dl>
</td>
<td width="60%">
<i>Instance1</i> is attached at the same altitude as <i>Instance2</i>. This can only occur if <i>Instance1</i> and <i>Instance2</i> are attached to different volumes or if <i>Instance1</i> and <i>Instance2</i> are pointers to the same instance. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>Less than zero</b></dt>
</dl>
</td>
<td width="60%">
<i>Instance1</i> is attached at a lower altitude than <i>Instance2</i>. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>Greater than zero</b></dt>
</dl>
</td>
<td width="60%">
<i>Instance1</i> is attached at a higher altitude than <i>Instance2</i>. 

</td>
</tr>
</table>
 




## -remarks



The minifilter driver instances that <i>Instance1</i> and <i>Instance2</i> point to can be instances of the same minifilter driver or different minifilter drivers. However, they must be attached to the same volume if the result returned by <b>FltCompareInstanceAltitudes</b> is to be meaningful. 

The term "altitude" refers to the position that an instance occupies (or should occupy) in the minifilter driver instance stack for a volume. The higher the altitude, the farther the instance is from the base file system in the stack. Only one instance can be attached at a given altitude on a given volume. 

Altitude is specified by an <i>altitude string</i>, which is a counted Unicode string that consists of one or more decimal digits from 0 through 9; the string can include a single decimal point. For example, "100.123456" and "03333" are valid altitude strings. 

The string "03333" represents a higher altitude than "100.123456" (Leading and trailing zeros are ignored.) In other words, an instance whose altitude is "03333" is farther from the base file system than an instance whose altitude is "100.123456". However, this comparison is only meaningful if both instances are attached to the same volume. 

To attach a minifilter driver instance to a volume, call <a href="https://msdn.microsoft.com/library/windows/hardware/ff541772">FltAttachVolume</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff541775">FltAttachVolumeAtAltitude</a>. 

To detach a minifilter driver instance from a volume, call <a href="https://msdn.microsoft.com/library/windows/hardware/ff542041">FltDetachVolume</a>. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff541772">FltAttachVolume</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541775">FltAttachVolumeAtAltitude</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541889">FltCompareInstanceAltitudes</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff542041">FltDetachVolume</a>
 

 

