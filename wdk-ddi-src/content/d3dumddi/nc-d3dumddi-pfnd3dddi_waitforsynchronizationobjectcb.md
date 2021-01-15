---
UID: NC:d3dumddi.PFND3DDDI_WAITFORSYNCHRONIZATIONOBJECTCB
title: PFND3DDDI_WAITFORSYNCHRONIZATIONOBJECTCB (d3dumddi.h)
description: The pfnWaitForSynchronizationObjectCb function inserts a wait for the specified synchronization objects in the specified context DMA stream.
old-location: display\pfnwaitforsynchronizationobjectcb.htm
tech.root: display
ms.date: 05/10/2018
keywords: ["PFND3DDDI_WAITFORSYNCHRONIZATIONOBJECTCB callback function"]
ms.keywords: D3Druntime_Functions_14f8a273-a662-41d3-b79b-1c779c5853a1.xml, PFND3DDDI_WAITFORSYNCHRONIZATIONOBJECTCB, PFND3DDDI_WAITFORSYNCHRONIZATIONOBJECTCB callback, d3dumddi/pfnWaitForSynchronizationObjectCb, display.pfnwaitforsynchronizationobjectcb, pfnWaitForSynchronizationObjectCb, pfnWaitForSynchronizationObjectCb callback function [Display Devices]
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Desktop
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
targetos: Windows
req.typenames: 
f1_keywords:
 - PFND3DDDI_WAITFORSYNCHRONIZATIONOBJECTCB
 - d3dumddi/PFND3DDDI_WAITFORSYNCHRONIZATIONOBJECTCB
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3dumddi.h
api_name:
 - PFND3DDDI_WAITFORSYNCHRONIZATIONOBJECTCB
product:
 - Windows
---

# PFND3DDDI_WAITFORSYNCHRONIZATIONOBJECTCB callback function


## -description

The <b>pfnWaitForSynchronizationObjectCb</b> function inserts a wait for the specified synchronization objects in the specified context DMA stream.

## -parameters

### -param hDevice

A handle to a display device (that is, the graphics context).

### -param Arg2

*pData* [in]

A pointer to a <a href="/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddicb_waitforsynchronizationobject">D3DDDICB_WAITFORSYNCHRONIZATIONOBJECT</a> structure that describes the synchronization objects and context DMA stream that are required to set up the wait.

## -returns

<b>pfnWaitForSynchronizationObjectCb</b> returns one of the following values:

| **Return code** | **Description** | 
|:--|:--|
| **S_OK** | The wait was successfully set up. | 
| **E_INVALIDARG** | Parameters were validated and determined to be incorrect. | 

 

This function might also return other HRESULT values.

## -remarks

<b>Direct3D Version 11 Note:  </b>For more information about how the driver calls <b>pfnWaitForSynchronizationObjectCb</b>, see <a href="/windows-hardware/drivers/display/changes-from-direct3d-10">Changes from Direct3D 10</a>.



For a code example of how to use the <b>pfnWaitForSynchronizationObjectCb</b> function, see <a href="/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_signalsynchronizationobjectcb">pfnSignalSynchronizationObjectCb</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddicb_waitforsynchronizationobject">D3DDDICB_WAITFORSYNCHRONIZATIONOBJECT</a>

