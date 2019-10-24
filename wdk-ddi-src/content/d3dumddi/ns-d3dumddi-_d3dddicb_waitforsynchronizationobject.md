---
UID: NS:d3dumddi._D3DDDICB_WAITFORSYNCHRONIZATIONOBJECT
title: _D3DDDICB_WAITFORSYNCHRONIZATIONOBJECT (d3dumddi.h)
description: The D3DDDICB_WAITFORSYNCHRONIZATIONOBJECT structure describes the parameters that are required to set up the wait in a call to the pfnWaitForSynchronizationObjectCb function.
old-location: display\d3dddicb_waitforsynchronizationobject.htm
tech.root: display
ms.assetid: 8f235fc4-924b-4cc4-858d-5009e69fae47
ms.date: 05/10/2018
ms.keywords: D3DDDICB_WAITFORSYNCHRONIZATIONOBJECT, D3DDDICB_WAITFORSYNCHRONIZATIONOBJECT structure [Display Devices], D3D_param_Structs_170af521-644c-4790-94dc-6836d880d620.xml, _D3DDDICB_WAITFORSYNCHRONIZATIONOBJECT, d3dumddi/D3DDDICB_WAITFORSYNCHRONIZATIONOBJECT, display.d3dddicb_waitforsynchronizationobject
ms.topic: struct
f1_keywords:
 - "d3dumddi/D3DDDICB_WAITFORSYNCHRONIZATIONOBJECT"
req.header: d3dumddi.h
req.include-header: D3dumddi.h
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
- d3dumddi.h
api_name:
- D3DDDICB_WAITFORSYNCHRONIZATIONOBJECT
product:
- Windows
targetos: Windows
req.typenames: D3DDDICB_WAITFORSYNCHRONIZATIONOBJECT
---

# _D3DDDICB_WAITFORSYNCHRONIZATIONOBJECT structure


## -description


The D3DDDICB_WAITFORSYNCHRONIZATIONOBJECT structure describes the parameters that are required to set up the wait in a call to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_waitforsynchronizationobjectcb">pfnWaitForSynchronizationObjectCb</a> function. 


## -struct-fields




### -field hContext

[in] A handle to a context that waits for the synchronization events in the array that the <b>ObjectHandleArray</b> member specifies to occur.


### -field ObjectCount

[in] The number of synchronization events in the <b>ObjectHandleArray</b> array. 


### -field ObjectHandleArray

[in] An array of handles to the synchronization events that the context that is specified by the <b>hContext</b> member waits for. The <b>D3DDDI_MAX_OBJECT_WAITED_ON</b> constant, which is defined as 32, indicates the maximum number of synchronization events that the context can wait for.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_waitforsynchronizationobjectcb">pfnWaitForSynchronizationObjectCb</a>
 

 

