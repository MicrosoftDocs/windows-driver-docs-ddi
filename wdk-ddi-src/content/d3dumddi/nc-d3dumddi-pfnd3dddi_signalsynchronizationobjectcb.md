---
UID: NC:d3dumddi.PFND3DDDI_SIGNALSYNCHRONIZATIONOBJECTCB
title: PFND3DDDI_SIGNALSYNCHRONIZATIONOBJECTCB
author: windows-driver-content
description: The pfnSignalSynchronizationObjectCb function inserts a signal on the specified synchronization objects in the specified context DMA stream.
old-location: display\pfnsignalsynchronizationobjectcb.htm
old-project: display
ms.assetid: 12ffa230-2c26-4cd3-ae83-f753a0b6ba38
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: D3Druntime_Functions_7bda6d91-797a-4f72-9182-e30b9fb1963a.xml, PFND3DDDI_SIGNALSYNCHRONIZATIONOBJECTCB, d3dumddi/pfnSignalSynchronizationObjectCb, display.pfnsignalsynchronizationobjectcb, pfnSignalSynchronizationObjectCb, pfnSignalSynchronizationObjectCb callback function [Display Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
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
req.typenames: DXGK_PTE
---

# PFND3DDDI_SIGNALSYNCHRONIZATIONOBJECTCB callback


## -description


The <b>pfnSignalSynchronizationObjectCb</b> function inserts a signal on the specified synchronization objects in the specified context DMA stream. 


## -parameters




### -param hDevice [in]

A handle to a display device (that is, the graphics context).


### -param *








#### - pData [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff544274">D3DDDICB_SIGNALSYNCHRONIZATIONOBJECT</a> structure that describes the synchronization objects and context DMA stream that signaling is set up on. 


## -returns



<b>pfnSignalSynchronizationObjectCb</b> returns one of the following values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>S_OK</b></dt>
</dl>
</td>
<td width="60%">
The signaling was successfully set up.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_INVALIDARG</b></dt>
</dl>
</td>
<td width="60%">
Parameters were validated and determined to be incorrect.

</td>
</tr>
</table>
 

This function might also return other HRESULT values.




## -remarks




<b>Direct3D Version 11 Note:  </b>For more information about how the driver calls <b>pfnSignalSynchronizationObjectCb</b>, see <a href="https://msdn.microsoft.com/014a5e44-f8c4-45c0-96e8-d82f37b8b28d">Changes from Direct3D 10</a>.




#### Examples

The following code example shows how to insert a signal on synchronization objects.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>HRESULT CD3DContext::SyncEngines(DWORD dwEngineReleasingControl, DWORD dwEngineAcquiringControl) {
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
}</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff544274">D3DDDICB_SIGNALSYNCHRONIZATIONOBJECT</a>
 

 

