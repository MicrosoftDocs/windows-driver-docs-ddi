---
UID: NE:d3dkmthk._D3DKMT_SCHEDULINGPRIORITYCLASS
title: _D3DKMT_SCHEDULINGPRIORITYCLASS (d3dkmthk.h)
description: The D3DKMT_SCHEDULINGPRIORITYCLASS enumeration type contains values that describe the scheduling priority for a process.
old-location: display\d3dkmt_schedulingpriorityclass.htm
ms.assetid: d42e37d0-0ba9-4b79-903d-fdbb478ab196
ms.date: 05/10/2018
ms.keywords: D3DKMT_SCHEDULINGPRIORITYCLASS, D3DKMT_SCHEDULINGPRIORITYCLASS enumeration [Display Devices], D3DKMT_SCHEDULINGPRIORITYCLASS_ABOVE_NORMAL, D3DKMT_SCHEDULINGPRIORITYCLASS_BELOW_NORMAL, D3DKMT_SCHEDULINGPRIORITYCLASS_HIGH, D3DKMT_SCHEDULINGPRIORITYCLASS_IDLE, D3DKMT_SCHEDULINGPRIORITYCLASS_NORMAL, D3DKMT_SCHEDULINGPRIORITYCLASS_REALTIME, OpenGL_Structs_4e331f58-8ed5-4aff-ac73-5af374f0d556.xml, _D3DKMT_SCHEDULINGPRIORITYCLASS, d3dkmthk/D3DKMT_SCHEDULINGPRIORITYCLASS, d3dkmthk/D3DKMT_SCHEDULINGPRIORITYCLASS_ABOVE_NORMAL, d3dkmthk/D3DKMT_SCHEDULINGPRIORITYCLASS_BELOW_NORMAL, d3dkmthk/D3DKMT_SCHEDULINGPRIORITYCLASS_HIGH, d3dkmthk/D3DKMT_SCHEDULINGPRIORITYCLASS_IDLE, d3dkmthk/D3DKMT_SCHEDULINGPRIORITYCLASS_NORMAL, d3dkmthk/D3DKMT_SCHEDULINGPRIORITYCLASS_REALTIME, display.d3dkmt_schedulingpriorityclass
ms.topic: enum
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- d3dkmthk.h
api_name:
- D3DKMT_SCHEDULINGPRIORITYCLASS
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: D3DKMT_SCHEDULINGPRIORITYCLASS
---

# _D3DKMT_SCHEDULINGPRIORITYCLASS enumeration


## -description


The D3DKMT_SCHEDULINGPRIORITYCLASS enumeration type contains values that describe the scheduling priority for a process.


## -enum-fields




### -field D3DKMT_SCHEDULINGPRIORITYCLASS_IDLE

The process is idle.


### -field D3DKMT_SCHEDULINGPRIORITYCLASS_BELOW_NORMAL

The scheduling priority of the process is below normal.


### -field D3DKMT_SCHEDULINGPRIORITYCLASS_NORMAL

The scheduling priority of the process is normal.


### -field D3DKMT_SCHEDULINGPRIORITYCLASS_ABOVE_NORMAL

The scheduling priority of the process is above normal.


### -field D3DKMT_SCHEDULINGPRIORITYCLASS_HIGH

The scheduling priority of the process is high.


### -field D3DKMT_SCHEDULINGPRIORITYCLASS_REALTIME

The scheduling priority of the process is in real time.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmthk/nf-d3dkmthk-d3dkmtgetprocessschedulingpriorityclass">D3DKMTGetProcessSchedulingPriorityClass</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmthk/nf-d3dkmthk-d3dkmtsetprocessschedulingpriorityclass">D3DKMTSetProcessSchedulingPriorityClass</a>
 

 

