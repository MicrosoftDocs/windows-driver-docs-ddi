---
UID: NF:storport.StorPortInitializeSpinlock
title: StorPortInitializeSpinlock function (storport.h)
description: The StorPortInitializeSpinLock routine initializes a variable of type STOR_KSPIN_LOCK.
old-location: storage\storportinitializespinlock.htm
tech.root: storage
ms.assetid: 150B1ED3-572A-4986-BED6-628ED6C54CCF
ms.date: 03/29/2018
ms.keywords: StorPortInitializeSpinlock, StorPortInitializeSpinlock routine [Storage Devices], storage.storportinitializespinlock, storport/StorPortInitializeSpinlock
ms.topic: function
req.header: storport.h
req.include-header: Storport.h
req.target-type: Universal
req.target-min-winverclnt: 
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
- storport.h
api_name:
- StorPortInitializeSpinlock
product:
- Windows
targetos: Windows
req.typenames: 
---

# StorPortInitializeSpinlock function


## -description


<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]

The <b>StorPortInitializeSpinLock </b>routine initializes a variable of type <b>STOR_KSPIN_LOCK</b>.


## -parameters




### -param HwDeviceExtension [in]

A pointer to the hardware device extension for the host bus adapter (HBA).


### -param Lock [out]

Pointer to a spin lock of type <b>STOR_KSPIN_LOCK</b>, for which the caller must provide the storage


## -returns



<b>StorPortInitializeSpinlock</b> returns one of the following status codes:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STOR_STATUS_NOT_IMPLEMENTED</b></dt>
</dl>
</td>
<td width="60%">
This function is not implemented on the active operating system.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STOR_STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The list items were removed successfully or the list is already empty.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STOR_STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
A pointer in <i>ListHead</i> or <i>Result</i> is <b>NULL</b>.

</td>
</tr>
</table>
 




## -remarks



This routine must be called before an initial call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/storport/nf-storport-storportacquirespinlock">StorPortAcquireSpinLock</a>, to any other support routine that requires a spin lock as an argument.

For more information about spin locks, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/spin-locks">Spin Locks</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/storport/nf-storport-storportacquiremsispinlock">StorPortAcquireMSISpinLock</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/storport/nf-storport-storportacquirespinlock">StorPortAcquireSpinLock</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/storport/nf-storport-storportreleasemsispinlock">StorPortReleaseMSISpinLock</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/storport/nf-storport-storportreleasespinlock">StorPortReleaseSpinLock</a>
 

 

