---
UID: NC:ks.PFNKSDEVICEIRPVOID
title: PFNKSDEVICEIRPVOID
author: windows-driver-content
description: An AVStream minidriver's IRP handling routine is called when these IRPs are dispatched by the device.IRP_MN_CANCEL_STOP_DEVICEIRP_MN_CANCEL_REMOVE_DEVICEIRP_MN_REMOVE_DEVICEIRP_MN_STOP_DEVICEIRP_MN_SURPRISE_REMOVAL
old-location: stream\avstrminidevicecancelstop.htm
old-project: stream
ms.assetid: 7c3cb6e2-707a-4f8d-84b7-fce1354c06af
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: stream.avstrminidevicecancelstop, AVStrMiniDeviceCancelStop, MyAVStrMiniDeviceIRP routine [Streaming Media Devices], MyAVStrMiniDeviceIRP, PFNKSDEVICEIRPVOID, PFNKSDEVICEIRPVOID, ks/MyAVStrMiniDeviceIRP, avstclbk_5b19ddf6-52f4-4d93-b5e1-7d7b5a41fe8b.xml
ms.prod: windows-hardware
ms.technology: windows-devices
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	ks.h
apiname:
-	MyAVStrMiniDeviceIRP
product: Windows
targetos: Windows
req.typenames: KEYWORDSELECTOR
---

# PFNKSDEVICEIRPVOID callback


## -description


An AVStream minidriver's IRP handling routine is called when these IRPs are dispatched by the device.


<a href="https://msdn.microsoft.com/library/windows/hardware/ff550826">IRP_MN_CANCEL_STOP_DEVICE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550823">IRP_MN_CANCEL_REMOVE_DEVICE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551738">IRP_MN_REMOVE_DEVICE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551755">IRP_MN_STOP_DEVICE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551760">IRP_MN_SURPRISE_REMOVAL</a>



## -prototype


````
PFNKSDEVICEIRPVOID MyAVStrMiniDeviceIRP;

void MyAVStrMiniDeviceIRP(
  _In_ PKSDEVICE Device,
  _In_ PIRP      Irp
)
{ ... }
````


## -parameters




### -param Device [in]

Pointer to the <a href="..\ks\ns-ks-_ksdevice.md">KSDEVICE</a> that dispatched the IRP.


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
The minidriver specifies this routine's address in the <b>CancelStop</b> member of its <a href="..\ks\ns-ks-_ksdevice_dispatch.md">KSDEVICE_DISPATCH</a> structure.

This routine is optional.

</td>
</tr>
<tr>
<td>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff550823">IRP_MN_CANCEL_REMOVE_DEVICE</a>
</td>
<td>
The minidriver specifies this routine's address in the <b>CancelRemove</b> member of its <a href="..\ks\ns-ks-_ksdevice_dispatch.md">KSDEVICE_DISPATCH</a> structure.

This routine is called when an <a href="https://msdn.microsoft.com/library/windows/hardware/ff550823">IRP_MN_CANCEL_REMOVE_DEVICE</a> is dispatched by the device.

This routine is optional.

</td>
</tr>
<tr>
<td>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff551738">IRP_MN_REMOVE_DEVICE</a>
</td>
<td>
The minidriver specifies this routine's address in the <b>MiniRemove</b> member of its <a href="..\ks\ns-ks-_ksdevice_dispatch.md">KSDEVICE_DISPATCH</a> structure.

AVStream calls this routine when an <a href="https://msdn.microsoft.com/library/windows/hardware/ff551738">IRP_MN_REMOVE_DEVICE</a> is dispatched by the device. Typically, it will be provided by minidrivers that must free device-associated resources upon device removal. This routine is optional.

</td>
</tr>
<tr>
<td>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff551755">IRP_MN_STOP_DEVICE</a>
</td>
<td>
The minidriver specifies this routine's address in the <b>Stop</b> member of its <a href="..\ks\ns-ks-_ksdevice_dispatch.md">KSDEVICE_DISPATCH</a> structure.

This is usually provided by minidrivers that need to detach from previously assigned resources before completing a stop operation.

This routine is optional.

</td>
</tr>
<tr>
<td>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff551760">IRP_MN_SURPRISE_REMOVAL</a>
</td>
<td>
The minidriver specifies this routine's address in the <b>SurpriseRemoval</b> member of its <a href="..\ks\ns-ks-_ksdevice_dispatch.md">KSDEVICE_DISPATCH</a> structure.

This routine is optional.

</td>
</tr>
</table> 



## -see-also

<a href="..\ks\ns-ks-_ksdevice.md">KSDEVICE</a>

<a href="..\ks\ns-ks-_ksdevice_dispatch.md">KSDEVICE_DISPATCH</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20PFNKSDEVICEIRPVOID routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

