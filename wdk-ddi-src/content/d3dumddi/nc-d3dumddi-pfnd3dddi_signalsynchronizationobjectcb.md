---
UID: NC:d3dumddi.PFND3DDDI_SIGNALSYNCHRONIZATIONOBJECTCB
title: PFND3DDDI_SIGNALSYNCHRONIZATIONOBJECTCB
description: The pfnSignalSynchronizationObjectCb function inserts a signal on the specified synchronization objects in the specified context DMA stream.
old-location: display\pfnsignalsynchronizationobjectcb.htm
tech.root: display
ms.assetid: 12ffa230-2c26-4cd3-ae83-f753a0b6ba38
ms.date: 05/10/2018
ms.keywords: D3Druntime_Functions_7bda6d91-797a-4f72-9182-e30b9fb1963a.xml, PFND3DDDI_SIGNALSYNCHRONIZATIONOBJECTCB, PFND3DDDI_SIGNALSYNCHRONIZATIONOBJECTCB callback, d3dumddi/pfnSignalSynchronizationObjectCb, display.pfnsignalsynchronizationobjectcb, pfnSignalSynchronizationObjectCb, pfnSignalSynchronizationObjectCb callback function [Display Devices]
ms.topic: callback
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	d3dumddi.h
api_name:
-	pfnSignalSynchronizationObjectCb
product:
- Windows
targetos: Windows
req.typenames: 
---

# PFND3DDDI_SIGNALSYNCHRONIZATIONOBJECTCB callback function


## -description


The <b>pfnSignalSynchronizationObjectCb</b> function inserts a signal on the specified synchronization objects in the specified context DMA stream. 


## -parameters




### -param hDevice [in]

A handle to a display device (that is, the graphics context).


### -param *


*pData* [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff544274">D3DDDICB_SIGNALSYNCHRONIZATIONOBJECT</a> structure that describes the synchronization objects and context DMA stream that signaling is set up on. 


## -returns



<b>pfnSignalSynchronizationObjectCb</b> returns one of the following values:

|Return code|Description|
|--- |--- |
|S_OK|The signaling was successfully set up.|
|E_INVALIDARG|Parameters were validated and determined to be incorrect.|
 

This function might also return other HRESULT values.




## -remarks




<b>Direct3D Version 11 Note:  </b>For more information about how the driver calls <b>pfnSignalSynchronizationObjectCb</b>, see <a href="https://msdn.microsoft.com/014a5e44-f8c4-45c0-96e8-d82f37b8b28d">Changes from Direct3D 10</a>.




#### Examples

The following code example shows how to insert a signal on synchronization objects.

```cpp
HRESULT CD3DContext::SyncEngines(DWORD dwEngineReleasingControl, DWORD dwEngineAcquiringControl) {
    HRESULT hr;
    D3DDDICB_WAITFORSYNCHRONIZATIONOBJECT   sWaitObject;
    D3DDDICB_SIGNALSYNCHRONIZATIONOBJECT    sSignalObject;

    sSignalObject.hContext = m_sContexts[dwEngineReleasingControl].hContext;
    sSignalObject.ObjectCount = 1;
    sSignalObject.ObjectHandleArray[0] = m_hEngineSyncObject;
    hr = m_d3dCallbacks.pfnSignalSynchronizationObjectCb(m_hD3D, &amp;sSignalObject);
    if (FAILED(hr)) {
        DBG_BREAK;
        return hr;
    }
    sWaitObject.hContext = m_sContexts[dwEngineAcquiringControl].hContext;
    sWaitObject.ObjectCount = 1;
    sWaitObject.ObjectHandleArray[0] = m_hEngineSyncObject;
    hr = m_d3dCallbacks.pfnWaitForSynchronizationObjectCb(m_hD3D, &amp;sWaitObject);
    if (FAILED(hr)) {
        DBG_BREAK;        
    }
    return hr;
}
```


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff544274">D3DDDICB_SIGNALSYNCHRONIZATIONOBJECT</a>
 

 

