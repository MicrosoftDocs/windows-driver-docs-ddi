---
UID: NS:ks._KSPIN_DISPATCH
title: "_KSPIN_DISPATCH"
author: windows-driver-content
description: The KSPIN_DISPATCH structure describes the callbacks for which clients can register in order to receive notification of pin events.
old-location: stream\kspin_dispatch.htm
old-project: stream
ms.assetid: 6c4aea1f-e788-49c7-91c0-831c87c6fd39
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: "*PKSPIN_DISPATCH, KSPIN_DISPATCH, KSPIN_DISPATCH structure [Streaming Media Devices], PKSPIN_DISPATCH, PKSPIN_DISPATCH structure pointer [Streaming Media Devices], _KSPIN_DISPATCH, avstruct_2ef1e08b-327f-476c-9c0b-804582f67815.xml, ks/KSPIN_DISPATCH, ks/PKSPIN_DISPATCH, stream.kspin_dispatch"
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
-	KSPIN_DISPATCH
product: Windows
targetos: Windows
req.typenames: KSPIN_DISPATCH, *PKSPIN_DISPATCH
---

# _KSPIN_DISPATCH structure


## -description


The KSPIN_DISPATCH structure describes the callbacks for which clients can register in order to receive notification of pin events.


## -syntax


````
typedef struct _KSPIN_DISPATCH {
  PFNKSPINIRP                Create;
  PFNKSPINIRP                Close;
  PFNKSPIN                   Process;
  PFNKSPINVOID               Reset;
  PFNKSPINSETDATAFORMAT      SetDataFormat;
  PFNKSPINSETDEVICESTATE     SetDeviceState;
  PFNKSPIN                   Connect;
  PFNKSPINVOID               Disconnect;
  const KSCLOCK_DISPATCH     *Clock;
  const KSALLOCATOR_DISPATCH *Allocator;
} KSPIN_DISPATCH, *PKSPIN_DISPATCH;
````


## -struct-fields




### -field Create

A pointer to a minidriver-supplied <a href="..\ks\nc-ks-pfnkspinirp.md">AVStrMiniPinCreate</a> callback routine. Optional. Can be <b>NULL</b>.


### -field Close

A pointer to a minidriver-supplied <a href="https://msdn.microsoft.com/library/windows/hardware/ff556329">AVStrMiniPinClose</a> callback routine. Optional. Can be <b>NULL</b>.


### -field Process

A pointer to a minidriver-supplied <a href="..\ks\nc-ks-pfnkspin.md">AVStrMiniPinProcess</a> callback routine. Optional. Can be <b>NULL</b>.


### -field Reset

A pointer to a minidriver-supplied <a href="https://msdn.microsoft.com/library/windows/hardware/ff556354">AVStrMiniPinReset</a> callback routine. Optional. Can be <b>NULL</b>.


### -field SetDataFormat

A pointer to a minidriver-supplied <a href="..\ks\nc-ks-pfnkspinsetdataformat.md">AVStrMiniPinSetDataFormat</a> callback routine. Optional. Can be <b>NULL</b>.


### -field SetDeviceState

A pointer to a minidriver-supplied <a href="..\ks\nc-ks-pfnkspinsetdevicestate.md">AVStrMiniPinSetDeviceState</a> callback routine. Optional. Can be <b>NULL</b>.


### -field Connect

A pointer to a minidriver-supplied <a href="https://msdn.microsoft.com/library/windows/hardware/ff556332">AVStrMiniPinConnect</a> callback routine. Optional. Can be <b>NULL</b>.


### -field Disconnect

A pointer to a minidriver-supplied <a href="..\ks\nc-ks-pfnkspinvoid.md">AVStrMiniPinDisconnect</a> callback routine. Optional. Can be <b>NULL</b>.


### -field Clock

A pointer to a <a href="..\ks\ns-ks-_ksclock_dispatch.md">KSCLOCK_DISPATCH</a> structure. Specify this member for a pin that exposes a clock. Optional. Can be <b>NULL</b>.


### -field Allocator

A pointer to a <a href="..\ks\ns-ks-_ksallocator_dispatch.md">KSALLOCATOR_DISPATCH</a> structure. Specify this member for a pin that is capable of performing kernel-level allocation. Optional. Can be <b>NULL</b>.


## -remarks



Any of the callback pointers can be <b>NULL</b>, indicating that the minidriver does not require to receive notification for this particular dispatch.

If the minidriver needs to determine whether it has been signaled to go to a specific state (for example KSSTATE_RUN), comparing the value of the <b>DeviceState</b> member of <a href="..\ks\ns-ks-_kspin.md">KSPIN</a> to <b>KSSTATE_RUN</b> is not a reliable method of doing this. <b>DeviceState</b> refers to the state to which the pin has been signaled to go, not the pipe. To perform the above reliably, instead create a variable in the <b>SetDeviceState</b> callback of this structure and then check this variable to make the determination.




## -see-also

<a href="..\ks\ns-ks-_kspin.md">KSPIN</a>



<a href="..\ks\ns-ks-_ksclock_dispatch.md">KSCLOCK_DISPATCH</a>



<a href="..\ks\ns-ks-_ksallocator_dispatch.md">KSALLOCATOR_DISPATCH</a>



<a href="..\ks\nf-ks-kscompletependingrequest.md">KsCompletePendingRequest</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KSPIN_DISPATCH structure%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

