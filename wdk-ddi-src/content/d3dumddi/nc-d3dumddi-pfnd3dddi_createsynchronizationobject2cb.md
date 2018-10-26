---
UID: NC:d3dumddi.PFND3DDDI_CREATESYNCHRONIZATIONOBJECT2CB
title: PFND3DDDI_CREATESYNCHRONIZATIONOBJECT2CB
author: windows-driver-content
description: Creates a GPU synchronization object that a device context can signal and wait for. Used by WDDM 1.2 and later user-mode display drivers.
old-location: display\pfncreatesynchronizationobject2cb.htm
tech.root: display
ms.assetid: 9B0F058C-B71F-4A4F-A053-F9381A5FD3A8
ms.date: 05/10/2018
ms.keywords: PFND3DDDI_CREATESYNCHRONIZATIONOBJECT2CB, PFND3DDDI_CREATESYNCHRONIZATIONOBJECT2CB callback, d3dumddi/pfnCreateSynchronizationObject2Cb, display.pfncreatesynchronizationobject2cb, pfnCreateSynchronizationObject2Cb, pfnCreateSynchronizationObject2Cb callback function [Display Devices]
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
-	pfnCreateSynchronizationObject2Cb
product:
- Windows
targetos: Windows
req.typenames: 
---

# PFND3DDDI_CREATESYNCHRONIZATIONOBJECT2CB callback function


## -description


Creates a GPU synchronization object that a device context can signal and wait for. Used by WDDM 1.2 and later user-mode display drivers.


## -parameters




### -param hDevice [in]

A handle to the display device (that is, the graphics context) that will own the synchronization object that <i>pfnCreateSynchronizationObject2Cb</i> creates.


### -param *








*pData* [in, out]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/hh451156">D3DDDICB_CREATESYNCHRONIZATIONOBJECT2</a> structure that describes the synchronization object to create.


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
The synchronization object was successfully created.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_OUTOFMEMORY</b></dt>
</dl>
</td>
<td width="60%">

The function could not allocate memory that was required for it to complete.

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



The <i>pfnCreateSynchronizationObject2Cb</i> function returns a kernel-mode handle to the newly created synchronization object in the <b>hSyncObject</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/hh451156">D3DDDICB_CREATESYNCHRONIZATIONOBJECT2</a> structure that the <i>pData</i> parameter points to. The user-mode display driver passes this handle in calls to the following functions:

<ul>
<li>

<a href="https://msdn.microsoft.com/7ba549a2-f165-4b5e-8cf4-ab707222532c">pfnDestroySynchronizationObjectCb</a>


</li>
<li>

<a href="https://msdn.microsoft.com/12ffa230-2c26-4cd3-ae83-f753a0b6ba38">pfnSignalSynchronizationObjectCb</a>


</li>
<li>

<a href="https://msdn.microsoft.com/01B5E793-D075-42B5-9ADF-D033249AEE9F">pfnSignalSynchronizationObject2Cb</a>


</li>
<li>

<a href="https://msdn.microsoft.com/d33ca665-897d-4e99-b9a6-b794127fecfd">pfnWaitForSynchronizationObjectCb</a>


</li>
<li>

<a href="https://msdn.microsoft.com/4542C49F-C26C-45BE-B961-C5F65BDA78CF">pfnWaitForSynchronizationObject2Cb</a>


</li>
</ul>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh451156">D3DDDICB_CREATESYNCHRONIZATIONOBJECT2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544512">D3DDDI_DEVICECALLBACKS</a>



<a href="https://msdn.microsoft.com/7ba549a2-f165-4b5e-8cf4-ab707222532c">pfnDestroySynchronizationObjectCb</a>



<a href="https://msdn.microsoft.com/01B5E793-D075-42B5-9ADF-D033249AEE9F">pfnSignalSynchronizationObject2Cb</a>



<a href="https://msdn.microsoft.com/4542C49F-C26C-45BE-B961-C5F65BDA78CF">pfnWaitForSynchronizationObject2Cb</a>
 

 

