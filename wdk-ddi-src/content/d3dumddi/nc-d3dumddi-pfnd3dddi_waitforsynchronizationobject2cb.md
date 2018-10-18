---
UID: NC:d3dumddi.PFND3DDDI_WAITFORSYNCHRONIZATIONOBJECT2CB
title: PFND3DDDI_WAITFORSYNCHRONIZATIONOBJECT2CB
author: windows-driver-content
description: Inserts a wait command for the specified synchronization objects in the specified context command stream. Used by Windows Display Driver Model (WDDM) 1.2 and later user-mode display drivers.
old-location: display\pfnwaitforsynchronizationobject2cb.htm
tech.root: display
ms.assetid: 4542C49F-C26C-45BE-B961-C5F65BDA78CF
ms.date: 5/10/2018
ms.keywords: PFND3DDDI_WAITFORSYNCHRONIZATIONOBJECT2CB, PFND3DDDI_WAITFORSYNCHRONIZATIONOBJECT2CB callback, d3dumddi/pfnWaitForSynchronizationObject2Cb, display.pfnwaitforsynchronizationobject2cb, pfnWaitForSynchronizationObject2Cb, pfnWaitForSynchronizationObject2Cb callback function [Display Devices]
ms.topic: callback
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Desktop
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
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	d3dumddi.h
api_name:
-	pfnWaitForSynchronizationObject2Cb
product:
- Windows
targetos: Windows
req.typenames: 
---

# PFND3DDDI_WAITFORSYNCHRONIZATIONOBJECT2CB callback function


## -description


Inserts a wait command for the specified synchronization objects in the specified context command stream. Used by Windows Display Driver Model (WDDM) 1.2 and later user-mode display drivers.


## -parameters




### -param hDevice [in]

A handle to a display device (that is, the graphics context).


### -param *








*pData* [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/hh451167">D3DDDICB_WAITFORSYNCHRONIZATIONOBJECT2</a> structure that describes the synchronization objects and context DMA stream that are required to set up the wait.


## -returns




      Returns one of the following values:

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
The wait was successfully set up.

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



The <a href="https://msdn.microsoft.com/9B0F058C-B71F-4A4F-A053-F9381A5FD3A8">pfnCreateSynchronizationObject2Cb</a> function returns a kernel-mode handle to the newly created synchronization object in the <b>hSyncObject</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/hh451156">D3DDDICB_CREATESYNCHRONIZATIONOBJECT2</a> structure that the <i>pData</i> parameter points to. The user-mode display driver passes this handle in calls to the following functions:

<ul>
<li>

<a href="https://msdn.microsoft.com/7ba549a2-f165-4b5e-8cf4-ab707222532c">pfnDestroySynchronizationObjectCb</a>


</li>
<li>

<a href="https://msdn.microsoft.com/01B5E793-D075-42B5-9ADF-D033249AEE9F">pfnSignalSynchronizationObject2Cb</a>


</li>
<li>
<i>pfnWaitForSynchronizationObject2Cb</i>

</li>
</ul>
Do not call this function if the synchronization object is of type <b>D3DDDI_CPU_NOTIFICATION</b>—namely, the <b>Type</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff544658">D3DDDI_SYNCHRONIZATIONOBJECTINFO2</a> structure has a value of <b>D3DDDI_CPU_NOTIFICATION</b>.<a href="https://msdn.microsoft.com/7ba549a2-f165-4b5e-8cf4-ab707222532c">pfnDestroySynchronizationObjectCb</a>





## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh451156">D3DDDICB_CREATESYNCHRONIZATIONOBJECT2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544512">D3DDDI_DEVICECALLBACKS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544658">D3DDDI_SYNCHRONIZATIONOBJECTINFO2</a>



<a href="https://msdn.microsoft.com/9B0F058C-B71F-4A4F-A053-F9381A5FD3A8">pfnCreateSynchronizationObject2Cb</a>



<a href="https://msdn.microsoft.com/7ba549a2-f165-4b5e-8cf4-ab707222532c">pfnDestroySynchronizationObjectCb</a>



<a href="https://msdn.microsoft.com/01B5E793-D075-42B5-9ADF-D033249AEE9F">pfnSignalSynchronizationObject2Cb</a>
 

 

