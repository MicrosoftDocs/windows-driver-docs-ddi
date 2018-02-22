---
UID: NF:d3dkmthk.D3DKMTUnlock
title: D3DKMTUnlock function
author: windows-driver-content
description: The D3DKMTUnlock function unlocks a list of allocations.
old-location: display\d3dkmtunlock.htm
old-project: display
ms.assetid: d672d99a-973f-46b3-b46c-cb0a82a85ede
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: OpenGL_Functions_6741960d-1f19-4000-948c-aeb71330eb1e.xml, d3dkmthk/D3DKMTUnlock, display.d3dkmtunlock, D3DKMTUnlock, D3DKMTUnlock function [Display Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Universal
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
req.lib: Gdi32.lib
req.dll: Gdi32.dll
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	Gdi32.dll
-	API-MS-Win-dx-d3dkmt-l1-1-0.dll
-	API-MS-Win-dx-d3dkmt-l1-1-1.dll
-	API-MS-Win-DX-D3DKMT-L1-1-2.dll
apiname:
-	D3DKMTUnlock
product: Windows
targetos: Windows
req.typenames: D3DKMT_DRIVERVERSION
---

# D3DKMTUnlock function


## -description


The <b>D3DKMTUnlock</b> function unlocks a list of allocations.


## -syntax


````
NTSTATUS APIENTRY D3DKMTUnlock(
  _In_ const D3DKMT_UNLOCK *pData
);
````


## -parameters




### -param D3DKMT_UNLOCK

TBD




#### - pData [in]

A pointer to a <a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_unlock.md">D3DKMT_UNLOCK</a> structure that describes a list of allocations to unlock.


## -returns



<b>D3DKMTUnlock</b> returns one of the following values;

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The allocations were successfully unlocked.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
Parameters were validated and determined to be incorrect.

</td>
</tr>
</table>
 

This function might also return other NTSTATUS values.




## -remarks



All of the allocations that the <b>D3DKMTUnlock</b> function unlocks must belong to the same device.


#### Examples

The following code examples demonstrates how an OpenGL ICD can use <b>D3DKMTUnlock</b> to unlock three allocations.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>HRESULT UnlockThree(D3DKMT_HANDLE hDevice, 
                    D3DKMT_HANDLE hAllocation1, 
                    D3DKMT_HANDLE hAllocation2, 
                    D3DKMT_HANDLE hAllocation3) 
{
    D3DKMT_HANDLE AllocationArray[3];
    D3DKMT_UNLOCK UnlockData;

    AllocationArray[0] = hAllocation1;
    AllocationArray[1] = hAllocation2;
    AllocationArray[2] = hAllocation3;

    UnlockData.hDevice = hDevice;
    UnlockData.NumAllocations = 3;
    UnlockData.phAllocations = AllocationArray;

    if (NT_SUCCESS((*pfnKTUnlock)(&amp;UnlockData))) {
        return S_OK;
    }
    return E_FAIL;
}</pre>
</td>
</tr>
</table></span></div>



## -see-also

<a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_unlock.md">D3DKMT_UNLOCK</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMTUnlock function%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

