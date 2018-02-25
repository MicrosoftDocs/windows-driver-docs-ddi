---
UID: NC:ks.PFNKSDEVICEQUERYCAPABILITIES
title: PFNKSDEVICEQUERYCAPABILITIES
author: windows-driver-content
description: An AVStream minidriver's AVStrMiniDeviceQueryCapabilities routine is called when an IRP_MN_QUERY_CAPABILITIES is dispatched by the device.
old-location: stream\avstrminidevicequerycapabilities.htm
old-project: stream
ms.assetid: 12084f07-5b6a-44d4-8ab3-325309e69372
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: AVStrMiniDeviceQueryCapabilities, AVStrMiniDeviceQueryCapabilities routine [Streaming Media Devices], PFNKSDEVICEQUERYCAPABILITIES, avstclbk_6078ead8-c11e-4f25-9742-21740e9a9da8.xml, ks/AVStrMiniDeviceQueryCapabilities, stream.avstrminidevicequerycapabilities
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
-	AVStrMiniDeviceQueryCapabilities
product: Windows
targetos: Windows
req.typenames: SOUNDDETECTOR_PATTERNHEADER
---

# PFNKSDEVICEQUERYCAPABILITIES callback


## -description


An AVStream minidriver's <i>AVStrMiniDeviceQueryCapabilities</i> routine is called when an <a href="https://msdn.microsoft.com/library/windows/hardware/ff551664">IRP_MN_QUERY_CAPABILITIES</a> is dispatched by the device.


## -prototype


````
PFNKSDEVICEQUERYCAPABILITIES AVStrMiniDeviceQueryCapabilities;

NTSTATUS AVStrMiniDeviceQueryCapabilities(
  _In_    PKSDEVICE            Device,
  _In_    PIRP                 Irp,
  _Inout_ PDEVICE_CAPABILITIES Capabilities
)
{ ... }
````


## -parameters




### -param Device [in]

Pointer to the <a href="..\ks\ns-ks-_ksdevice.md">KSDEVICE</a> that dispatched the <a href="https://msdn.microsoft.com/library/windows/hardware/ff551664">IRP_MN_QUERY_CAPABILITIES</a>.


### -param Irp [in]

The <a href="https://msdn.microsoft.com/library/windows/hardware/ff551664">IRP_MN_QUERY_CAPABILITIES</a> issued by <i>Device</i>.


### -param Capabilities [in, out]

Pointer to the DEVICE_CAPABILITIES structure that describes PnP and Power capabilities of <i>Device</i>.


## -returns



Should return STATUS_SUCCESS or the error code that was returned from the attempt to perform the operation. Return success if providing query capabilities. If not, return an appropriate error code. Do not return STATUS_PENDING.




## -remarks



The minidriver specifies this routine's address in the <b>QueryCapabilities</b> member of its <a href="..\ks\ns-ks-_ksdevice_dispatch.md">KSDEVICE_DISPATCH</a> structure.

This routine is called when an <a href="https://msdn.microsoft.com/library/windows/hardware/ff551664">IRP_MN_QUERY_CAPABILITIES</a> is dispatched by the device. It will usually be provided by minidrivers that need to supply information regarding power management capabilities. This routine is optional.




## -see-also

<a href="..\ks\ns-ks-_ksdevice.md">KSDEVICE</a>



<a href="..\ks\ns-ks-_ksdevice_dispatch.md">KSDEVICE_DISPATCH</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20PFNKSDEVICEQUERYCAPABILITIES routine%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

