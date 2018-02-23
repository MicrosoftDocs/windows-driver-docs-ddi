---
UID: NS:ks._KSDEVICE_DISPATCH
title: "_KSDEVICE_DISPATCH"
author: windows-driver-content
description: The KSDEVICE_DISPATCH structure describes the callbacks that a client can provide to receive notification of device creation and PnP events.
old-location: stream\ksdevice_dispatch.htm
old-project: stream
ms.assetid: 1ae7af1d-5e1c-4728-82c5-efc8d60b5df6
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: "_KSDEVICE_DISPATCH, PKSDEVICE_DISPATCH, avstruct_7ceb03b7-6973-46bd-ad3e-32fdce7f4f11.xml, stream.ksdevice_dispatch, KSDEVICE_DISPATCH structure [Streaming Media Devices], *PKSDEVICE_DISPATCH, KSDEVICE_DISPATCH, PKSDEVICE_DISPATCH structure pointer [Streaming Media Devices], ks/PKSDEVICE_DISPATCH, ks/KSDEVICE_DISPATCH"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ks.h
req.include-header: Ks.h
req.target-type: Windows
req.target-min-winverclnt: Available in Microsoft Windows XP and later operating systems and in Microsoft DirectX 8.0 and later versions.
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
-	HeaderDef
apilocation:
-	ks.h
apiname:
-	KSDEVICE_DISPATCH
product: Windows
targetos: Windows
req.typenames: KSDEVICE_DISPATCH, *PKSDEVICE_DISPATCH
---

# _KSDEVICE_DISPATCH structure


## -description


The KSDEVICE_DISPATCH structure describes the callbacks that a client can provide to receive notification of device creation and PnP events.


## -syntax


````
typedef struct _KSDEVICE_DISPATCH {
  PFNKSDEVICECREATE            Add;
  PFNKSDEVICEPNPSTART          Start;
  PFNKSDEVICE                  PostStart;
  PFNKSDEVICEIRP               QueryStop;
  PFNKSDEVICEIRPVOID           CancelStop;
  PFNKSDEVICEIRPVOID           Stop;
  PFNKSDEVICEIRP               QueryRemove;
  PFNKSDEVICEIRPVOID           CancelRemove;
  PFNKSDEVICEIRPVOID           Remove;
  PFNKSDEVICEQUERYCAPABILITIES QueryCapabilities;
  PFNKSDEVICEIRPVOID           SurpriseRemoval;
  PFNKSDEVICEQUERYPOWER        QueryPower;
  PFNKSDEVICESETPOWER          SetPower;
  PFNKSDEVICEIRP               QueryInterface;
} KSDEVICE_DISPATCH, *PKSDEVICE_DISPATCH;
````


## -struct-fields




### -field Add

Optional. Can be <b>NULL</b>. A pointer to a minidriver-supplied <a href="..\ks\nc-ks-pfnksdevicecreate.md">AVStrMiniDeviceAdd</a> callback routine.


### -field Start

Optional. Can be <b>NULL</b>. A pointer to a minidriver-supplied <a href="..\ks\nc-ks-pfnksdevicepnpstart.md">AVStrMiniDeviceStart</a> callback routine.


### -field PostStart

Optional. Can be <b>NULL</b>. A pointer to a minidriver-supplied <a href="..\ks\nc-ks-pfnksdevice.md">AVStrMiniDevicePostStart</a> callback routine.


### -field QueryStop

Optional. Can be <b>NULL</b>. A pointer to a minidriver-supplied <a href="https://msdn.microsoft.com/library/windows/hardware/ff554299">AVStrMiniDeviceQueryStop</a> callback routine.


### -field CancelStop

Optional. Can be <b>NULL</b>. A pointer to a minidriver-supplied <a href="..\ks\nc-ks-pfnksdeviceirpvoid.md">AVStrMiniDeviceCancelStop</a> callback routine.


### -field Stop

Optional. Can be <b>NULL</b>. A pointer to a minidriver-supplied <a href="https://msdn.microsoft.com/library/windows/hardware/ff556301">AVStrMiniDeviceStop</a> callback routine.


### -field QueryRemove

Optional. Can be <b>NULL</b>. A pointer to a minidriver-supplied <a href="..\ks\nc-ks-pfnksdeviceirp.md">AVStrMiniDeviceQueryRemove</a> callback routine.


### -field CancelRemove

Optional. Can be <b>NULL</b>. A pointer to a minidriver-supplied <a href="https://msdn.microsoft.com/library/windows/hardware/ff554278">AVStrMiniDeviceCancelRemove</a> callback routine.


### -field Remove

Optional. Can be <b>NULL</b>. A pointer to a minidriver-supplied <a href="https://msdn.microsoft.com/library/windows/hardware/ff554305">AVStrMiniDeviceRemove</a> callback routine.


### -field QueryCapabilities

Optional. Can be <b>NULL</b>. A pointer to a minidriver-supplied <a href="..\ks\nc-ks-pfnksdevicequerycapabilities.md">AVStrMiniDeviceQueryCapabilities</a> callback routine.


### -field SurpriseRemoval

Optional. Can be <b>NULL</b>. A pointer to a minidriver-supplied <a href="https://msdn.microsoft.com/library/windows/hardware/ff556304">AVStrMiniDeviceSurpriseRemoval</a> callback routine.


### -field QueryPower

Optional. can be <b>NULL</b>. A pointer to a minidriver-supplied <a href="..\ks\nc-ks-pfnksdevicequerypower.md">AVStrMiniDeviceQueryPower</a> callback routine.


### -field SetPower

Optional. Can be <b>NULL</b>. A pointer to a minidriver-supplied <a href="..\ks\nc-ks-pfnksdevicesetpower.md">AVStrMiniDeviceSetPower</a> callback routine.


### -field QueryInterface

Optional. Can be <b>NULL</b>. A pointer to a minidriver-supplied <a href="https://msdn.microsoft.com/library/windows/hardware/ff554290">AVStrMiniDeviceQueryInterface</a> callback routine.


## -remarks



In describing a device with the <a href="..\ks\ns-ks-_ksdevice_descriptor.md">KSDEVICE_DESCRIPTOR</a> structure, clients include a pointer to a dispatch table defined by this structure. Any member of this structure may be <b>NULL</b> indicating that the minidriver receives no notification for that particular message.




## -see-also

<a href="..\ks\ns-ks-_ksdevice_descriptor.md">KSDEVICE_DESCRIPTOR</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KSDEVICE_DISPATCH structure%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

