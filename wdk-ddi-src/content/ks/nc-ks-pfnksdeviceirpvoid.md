---
UID: NC:ks.PFNKSDEVICEIRPVOID
title: PFNKSDEVICEIRPVOID (ks.h)
description: An AVStream minidriver's IRP handling routine is called when these IRPs are dispatched by the device.IRP_MN_CANCEL_STOP_DEVICEIRP_MN_CANCEL_REMOVE_DEVICEIRP_MN_REMOVE_DEVICEIRP_MN_STOP_DEVICEIRP_MN_SURPRISE_REMOVAL
old-location: stream\avstrminidevicecancelstop.htm
tech.root: stream
ms.assetid: 7c3cb6e2-707a-4f8d-84b7-fce1354c06af
ms.date: 04/23/2018
ms.keywords: AVStrMiniDeviceCancelStop, MyAVStrMiniDeviceIRP, MyAVStrMiniDeviceIRP routine [Streaming Media Devices], PFNKSDEVICEIRPVOID, avstclbk_5b19ddf6-52f4-4d93-b5e1-7d7b5a41fe8b.xml, ks/MyAVStrMiniDeviceIRP, stream.avstrminidevicecancelstop
ms.topic: callback
req.header: ks.h
req.include-header: Ks.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Microsoft Windows XP and later operating systems and DirectX 8.0 and later DirectX versions.
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
- UserDefined
api_location:
- ks.h
api_name:
- MyAVStrMiniDeviceIRP
product:
- Windows
targetos: Windows
req.typenames: 
---

# PFNKSDEVICEIRPVOID callback function


## -description


An AVStream minidriver's IRP handling routine is called when these IRPs are dispatched by the device.


<a href="https://msdn.microsoft.com/library/windows/hardware/ff550826">IRP_MN_CANCEL_STOP_DEVICE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550823">IRP_MN_CANCEL_REMOVE_DEVICE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551738">IRP_MN_REMOVE_DEVICE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551755">IRP_MN_STOP_DEVICE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551760">IRP_MN_SURPRISE_REMOVAL</a>



## -parameters




### -param Device [in]

Pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff561681">KSDEVICE</a> that dispatched the IRP.


### -param Irp [in]

The IRP issued by <i>Device</i>.


## -returns



None




## -remarks



<table>
<tr>
<th>IRP</th>
<th>Description</th>
</tr>
<tr>
<td>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff550826">IRP_MN_CANCEL_STOP_DEVICE</a>
</td>
<td>
The minidriver specifies this routine's address in the <b>CancelStop</b> member of its <a href="https://msdn.microsoft.com/library/windows/hardware/ff561693">KSDEVICE_DISPATCH</a> structure.

This routine is optional.

</td>
</tr>
<tr>
<td>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff550823">IRP_MN_CANCEL_REMOVE_DEVICE</a>
</td>
<td>
The minidriver specifies this routine's address in the <b>CancelRemove</b> member of its <a href="https://msdn.microsoft.com/library/windows/hardware/ff561693">KSDEVICE_DISPATCH</a> structure.

This routine is called when an <a href="https://msdn.microsoft.com/library/windows/hardware/ff550823">IRP_MN_CANCEL_REMOVE_DEVICE</a> is dispatched by the device.

This routine is optional.

</td>
</tr>
<tr>
<td>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff551738">IRP_MN_REMOVE_DEVICE</a>
</td>
<td>
The minidriver specifies this routine's address in the <b>MiniRemove</b> member of its <a href="https://msdn.microsoft.com/library/windows/hardware/ff561693">KSDEVICE_DISPATCH</a> structure.

AVStream calls this routine when an <a href="https://msdn.microsoft.com/library/windows/hardware/ff551738">IRP_MN_REMOVE_DEVICE</a> is dispatched by the device. Typically, it will be provided by minidrivers that must free device-associated resources upon device removal. This routine is optional.

</td>
</tr>
<tr>
<td>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff551755">IRP_MN_STOP_DEVICE</a>
</td>
<td>
The minidriver specifies this routine's address in the <b>Stop</b> member of its <a href="https://msdn.microsoft.com/library/windows/hardware/ff561693">KSDEVICE_DISPATCH</a> structure.

This is usually provided by minidrivers that need to detach from previously assigned resources before completing a stop operation.

This routine is optional.

</td>
</tr>
<tr>
<td>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff551760">IRP_MN_SURPRISE_REMOVAL</a>
</td>
<td>
The minidriver specifies this routine's address in the <b>SurpriseRemoval</b> member of its <a href="https://msdn.microsoft.com/library/windows/hardware/ff561693">KSDEVICE_DISPATCH</a> structure.

This routine is optional.

</td>
</tr>
</table>
 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff561681">KSDEVICE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561693">KSDEVICE_DISPATCH</a>
 

 

