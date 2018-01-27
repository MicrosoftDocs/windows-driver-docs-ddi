---
UID: NC:ks.PFNKSDEVICECREATE
title: PFNKSDEVICECREATE
author: windows-driver-content
description: An AVStream minidriver's AVStrMiniDeviceAdd routine notifies the minidriver that AVStream's PnP AddDevice routine has completed.
old-location: stream\avstrminideviceadd.htm
old-project: stream
ms.assetid: 8f7168c3-0c28-4802-af34-45b46c1b6827
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: stream.avstrminideviceadd, AVStrMiniDeviceAdd, AVStrMiniDeviceAdd routine [Streaming Media Devices], AVStrMiniDeviceAdd, PFNKSDEVICECREATE, PFNKSDEVICECREATE, ks/AVStrMiniDeviceAdd, avstclbk_1cba196f-c0c6-42fb-8674-52e0fad4a337.xml
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
req.irql: PASSIVE_LEVEL (See Remarks section)
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	UserDefined
apilocation: 
-	ks.h
apiname: 
-	AVStrMiniDeviceAdd
product: Windows
targetos: Windows
req.typenames: KEYWORDSELECTOR
---

# PFNKSDEVICECREATE callback


## -description


An AVStream minidriver's <i>AVStrMiniDeviceAdd</i> routine notifies the minidriver that AVStream's PnP <i>AddDevice</i> routine has completed.


## -prototype


````
PFNKSDEVICECREATE AVStrMiniDeviceAdd;

NTSTATUS AVStrMiniDeviceAdd(
  _In_ PKSDEVICE Device
)
{ ... }
````


## -parameters




### -param Device [in]

Pointer to a <a href="..\ks\ns-ks-_ksdevice.md">KSDEVICE</a> structure describing the functional device object (FDO) that has just been created.


## -returns


Should return STATUS_SUCCESS or the error code that was returned from the attempt to perform the operation. If the minidriver returns failure status, the related <i>AddDevice</i> call will also fail. See the Remarks section below for more details.



## -remarks


The minidriver specifies this routine's address in the <b>Add</b> member of its <a href="..\ks\ns-ks-_ksdevice_dispatch.md">KSDEVICE_DISPATCH</a> structure.

AVStream calls <i>AVStrMiniDeviceAdd</i> from its default <i>AddDevice</i> routine, at <a href="..\ks\ns-ks-_ksdevice.md">KSDEVICE</a> initialization time. At the point at which this routine is called, the WDM device object (<a href="..\wdm\ns-wdm-_device_object.md">DEVICE_OBJECT</a>) has been created, the <b>KSDEVICE</b> structure has been instantiated and initialized, and the KS device header has been allocated.

Minidrivers can use this routine to associate context information with the AVStream device object, or to initialize a device extension.

If this routine returns an unsuccessful status code, AVStream's <i>AddDevice</i> routine will fail. STATUS_PENDING is not a legal return code because no IRP is involved. The routine is called at IRQL = PASSIVE_LEVEL only.

This routine is optional.



## -see-also

<a href="..\ks\ns-ks-_ksdevice_dispatch.md">KSDEVICE_DISPATCH</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20PFNKSDEVICECREATE routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

