---
UID: NS:d3dkmthk._D3DKMT_VIDSCH_ESCAPE
title: "_D3DKMT_VIDSCH_ESCAPE"
author: windows-driver-content
description: The D3DKMT_VIDSCH_ESCAPE structure describes how to control the graphics processing unit (GPU) scheduler (which is part of Dxgkrnl.sys) in a call to the D3DKMTEscape function.
old-location: display\d3dkmt_vidsch_escape.htm
ms.assetid: 8e19e8a1-0cb6-4d57-862c-2e3a785b949b
ms.date: 5/10/2018
ms.keywords: D3DKMT_VIDSCH_ESCAPE, D3DKMT_VIDSCH_ESCAPE structure [Display Devices], OpenGL_Structs_d668addb-7c4a-4f07-bf9b-71ccd4a216fa.xml, _D3DKMT_VIDSCH_ESCAPE, d3dkmthk/D3DKMT_VIDSCH_ESCAPE, display.d3dkmt_vidsch_escape
ms.topic: struct
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
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
-	d3dkmthk.h
api_name:
-	D3DKMT_VIDSCH_ESCAPE
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: D3DKMT_VIDSCH_ESCAPE
---

# _D3DKMT_VIDSCH_ESCAPE structure


## -description


<b>Do not use the D3DKMT_VIDSCH_ESCAPE structure; it is for testing purposes only.</b>

The D3DKMT_VIDSCH_ESCAPE structure describes how to control the graphics processing unit (GPU) scheduler (which is part of Dxgkrnl.sys) in a call to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff546940">D3DKMTEscape</a> function.


## -struct-fields




### -field Type

The escape type, of type <a href="https://msdn.microsoft.com/library/windows/hardware/dn914467">D3DKMT_VIDSCHESCAPETYPE</a>, which is reserved and should not be used in your driver.


### -field PreemptionControl

Enable or disable preemption.


### -field EnableContextDelay

Enable or disable context delay.


### -field TdrControl2


### -field TdrControl2.TdrControl

Control TDR.


### -field TdrControl2.NodeOrdinal

Valid if <b>TdrControl</b> is set to a value of <b>D3DKMT_TDRDBGCTRLTYPE_ENGINETDR</b>.


### -field SuspendScheduler

Suspend or resume scheduler (obsolete).


### -field TdrControl

Control TDR.


### -field SuspendTime

Time period to suspend.


### -field TdrLimit

 


### -field TdrLimit.Count

 


### -field TdrLimit.Time

 


### -field PfnControl

 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff546940">D3DKMTEscape</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547970">D3DKMT_ESCAPE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn914467">D3DKMT_VIDSCHESCAPETYPE</a>
 

 

