---
UID: NC:d3dkmthk.PFND3DKMT_ACQUIREKEYEDMUTEX2
title: PFND3DKMT_ACQUIREKEYEDMUTEX2 (d3dkmthk.h)
description: Acquires a keyed mutex object that includes private data.
old-location: display\d3dkmtacquirekeyedmutex2.htm
ms.assetid: 94ebfeb6-2035-4dd6-bbc9-ba82939b51ec
ms.date: 05/10/2018
keywords: ["PFND3DKMT_ACQUIREKEYEDMUTEX2 callback function"]
ms.keywords: D3DKMTAcquireKeyedMutex2, D3DKMTAcquireKeyedMutex2 callback function [Display Devices], PFND3DKMT_ACQUIREKEYEDMUTEX2, PFND3DKMT_ACQUIREKEYEDMUTEX2 callback, d3dkmthk/D3DKMTAcquireKeyedMutex2, display.d3dkmtacquirekeyedmutex2
f1_keywords:
 - "d3dkmthk/D3DKMTAcquireKeyedMutex2"
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Universal
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
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
- UserDefined
api_location:
- d3dkmthk.h
api_name:
- D3DKMTAcquireKeyedMutex2
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# PFND3DKMT_ACQUIREKEYEDMUTEX2 callback function


## -description


Acquires a keyed mutex object that includes private data.


## -parameters




### -param 

*pData* 

[in, out] A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/ns-d3dkmthk-_d3dkmt_acquirekeyedmutex2">D3DKMT_ACQUIREKEYEDMUTEX2</a> structure that specifies the keyed mutex object to acquire. 


## -returns



Returns one of the following values:

| **Return code** | **Description** | 
|:--|:--|
| **STATUS_SUCCESS** | The keyed mutex object was successfully acquired. | 
| **STATUS_DEVICE_REMOVED** | The graphics adapter was stopped or the display device was reset. | 
| **STATUS_INVALID_PARAMETER** | Parameters were validated and determined to be incorrect. | 
| **STATUS_NO_MEMORY** | [D3DKMTAcquireKeyedMutex2](https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/nf-d3dkmthk-d3dkmtacquirekeyedmutex2)  could not complete because of insufficient memory. | 

This function might also return other <b>NTSTATUS</b> values.




## -remarks



<b>D3DKMTAcquireKeyedMutex2</b> behaves like the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/nf-d3dkmthk-d3dkmtacquirekeyedmutex">D3DKMTAcquireKeyedMutex</a> function but lets the caller specify private data to associate with the keyed mutex.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/nf-d3dkmthk-d3dkmtacquirekeyedmutex">D3DKMTAcquireKeyedMutex</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/ns-d3dkmthk-_d3dkmt_acquirekeyedmutex2">D3DKMT_ACQUIREKEYEDMUTEX2</a>
 

 

