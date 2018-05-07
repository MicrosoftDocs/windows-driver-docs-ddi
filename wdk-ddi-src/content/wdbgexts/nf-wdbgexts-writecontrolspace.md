---
UID: NF:wdbgexts.WriteControlSpace
title: WriteControlSpace function
author: windows-driver-content
description: The WriteControlSpace function writes to the processor-specific control space of the current target.
old-location: debugger\writecontrolspace.htm
old-project: debugger
ms.assetid: 12ea119e-9d56-4a1d-a8c6-3999147dfaac
ms.author: windowsdriverdev
ms.date: 4/24/2018
ms.keywords: WdbgExts_Ref_ee59dfdc-d138-4f1b-8f5c-fb9e1d47bef2.xml, WriteControlSpace, WriteControlSpace function [Windows Debugging], debugger.writecontrolspace, wdbgexts/WriteControlSpace
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdbgexts.h
req.include-header: Wdbgexts.h, Dbgeng.h
req.target-type: Desktop
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
req.lib: 
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	wdbgexts.h
api_name:
-	WriteControlSpace
product:
- Windows
targetos: Windows
req.typenames: 
---

# WriteControlSpace function


## -description


The <b>WriteControlSpace</b> function writes to the processor-specific control space of the current target.


## -parameters




### -param processor

Specifies the index of the processor whose control space is to be written.


### -param address

Specifies the address of the control space.


### -param buf

Specifies the data to be written to the control space.


### -param size

Specifies the number of bytes to be written.  This is the number of bytes in the <i>buf</i> buffer.


## -returns



None




## -remarks



This function can only be called in kernel-mode debugging.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff553527">ReadControlSpace</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553532">ReadControlSpace64</a>
 

 

