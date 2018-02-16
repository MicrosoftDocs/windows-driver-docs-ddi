---
UID: NC:ks.PFNKSDEVICEQUERYPOWER
title: PFNKSDEVICEQUERYPOWER
author: windows-driver-content
description: AVStream calls a minidriver's AVStrMiniDeviceQueryPower routine when it receives an IRP_MN_QUERY_POWER request.
old-location: stream\avstrminidevicequerypower.htm
old-project: stream
ms.assetid: db839cde-cb3e-47f2-9a06-54e37ac7ac67
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: stream.avstrminidevicequerypower, AVStrMiniDeviceQueryPower, AVStrMiniDeviceQueryPower routine [Streaming Media Devices], AVStrMiniDeviceQueryPower, PFNKSDEVICEQUERYPOWER, PFNKSDEVICEQUERYPOWER, ks/AVStrMiniDeviceQueryPower, avstclbk_47f0fecd-9906-4582-9f1d-bb80a469ffa6.xml
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
-	AVStrMiniDeviceQueryPower
product: Windows
targetos: Windows
req.typenames: KEYWORDSELECTOR
---

# PFNKSDEVICEQUERYPOWER callback


## -description


AVStream calls a minidriver's <i>AVStrMiniDeviceQueryPower</i> routine when it receives an <a href="https://msdn.microsoft.com/library/windows/hardware/ff551699">IRP_MN_QUERY_POWER</a> request.


## -prototype


````
PFNKSDEVICEQUERYPOWER AVStrMiniDeviceQueryPower;

NTSTATUS AVStrMiniDeviceQueryPower(
  _In_ PKSDEVICE          Device,
  _In_ PIRP               Irp,
  _In_ DEVICE_POWER_STATE DeviceTo,
  _In_ DEVICE_POWER_STATE DeviceFrom,
  _In_ SYSTEM_POWER_STATE SystemTo,
  _In_ SYSTEM_POWER_STATE SystemFrom,
  _In_ POWER_ACTION       Action
)
{ ... }
````


## -parameters




### -param Device [in]

Pointer to the <a href="..\ks\ns-ks-_ksdevice.md">KSDEVICE</a> structure that dispatched the <a href="https://msdn.microsoft.com/library/windows/hardware/ff551699">IRP_MN_QUERY_POWER</a>.


### -param Irp [in]

Pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff551699">IRP_MN_QUERY_POWER</a> issued by <i>Device</i>.


### -param DeviceTo [in]

The power state requested by the issuer of <i>Irp</i>.


### -param DeviceFrom [in]

The current device power state.


### -param SystemTo [in]

System state to transition to, specified when a system power state transition is being queried. This value is unspecified if the call is due to a device power state change query.


### -param SystemFrom [in]

Current system state, specified when a system power state transition is being queried. This value is unspecified if the call is due to a device power state change query.


### -param Action [in]

Specifies additional information about the requested transition. Possible values are enumerators of the POWER_ACTION type.


## -returns



Should return STATUS_SUCCESS or the error code that was returned from the attempt to perform the operation. By returning STATUS_SUCCESS, the driver guarantees that it will not start any operation that would change its ability to set the requested power state. The driver should queue any IRP that would require such an operation until it completes a <a href="https://msdn.microsoft.com/library/windows/hardware/ff551744">IRP_MN_SET_POWER</a> that returns the device to an acceptable power state.




## -remarks



The power manager or a device power policy owner sends an <a href="https://msdn.microsoft.com/library/windows/hardware/ff551699">IRP_MN_QUERY_POWER</a> request to determine whether it can change the system or device power state (for example, to go to sleep).

If a driver fails an IRP_MN_QUERY_POWER request for a system power state, the power manager typically responds by issuing an <a href="https://msdn.microsoft.com/library/windows/hardware/ff551744">IRP_MN_SET_POWER</a>. Usually, this IRP will reaffirm the current system state. However, it is possible that drivers might receive an IRP_MN_SET_POWER to the queried state or to some other intermediate state. Drivers should be prepared to handle these situations.

The minidriver specifies this routine's address in the <b>QueryPower</b> member of its <a href="..\ks\ns-ks-_ksdevice_dispatch.md">KSDEVICE_DISPATCH</a> structure.

This routine is optional.




## -see-also

<a href="..\ks\ns-ks-_ksdevice_dispatch.md">KSDEVICE_DISPATCH</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551699">IRP_MN_QUERY_POWER</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20PFNKSDEVICEQUERYPOWER routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

