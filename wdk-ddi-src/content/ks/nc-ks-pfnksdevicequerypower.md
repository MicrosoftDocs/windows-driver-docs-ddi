---
UID: NC:ks.PFNKSDEVICEQUERYPOWER
title: PFNKSDEVICEQUERYPOWER (ks.h)
description: AVStream calls a minidriver's AVStrMiniDeviceQueryPower routine when it receives an IRP_MN_QUERY_POWER request.
old-location: stream\avstrminidevicequerypower.htm
tech.root: stream
ms.assetid: db839cde-cb3e-47f2-9a06-54e37ac7ac67
ms.date: 04/23/2018
ms.keywords: AVStrMiniDeviceQueryPower, AVStrMiniDeviceQueryPower routine [Streaming Media Devices], PFNKSDEVICEQUERYPOWER, avstclbk_47f0fecd-9906-4582-9f1d-bb80a469ffa6.xml, ks/AVStrMiniDeviceQueryPower, stream.avstrminidevicequerypower
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
- AVStrMiniDeviceQueryPower
product:
- Windows
targetos: Windows
req.typenames: 
---

# PFNKSDEVICEQUERYPOWER callback function


## -description


AVStream calls a minidriver's <i>AVStrMiniDeviceQueryPower</i> routine when it receives an <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mn-query-power">IRP_MN_QUERY_POWER</a> request.


## -parameters




### -param Device [in]

Pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/ns-ks-_ksdevice">KSDEVICE</a> structure that dispatched the <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mn-query-power">IRP_MN_QUERY_POWER</a>.


### -param Irp [in]

Pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mn-query-power">IRP_MN_QUERY_POWER</a> issued by <i>Device</i>.


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



Should return STATUS_SUCCESS or the error code that was returned from the attempt to perform the operation. By returning STATUS_SUCCESS, the driver guarantees that it will not start any operation that would change its ability to set the requested power state. The driver should queue any IRP that would require such an operation until it completes a <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mn-set-power">IRP_MN_SET_POWER</a> that returns the device to an acceptable power state.




## -remarks



The power manager or a device power policy owner sends an <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mn-query-power">IRP_MN_QUERY_POWER</a> request to determine whether it can change the system or device power state (for example, to go to sleep).

If a driver fails an IRP_MN_QUERY_POWER request for a system power state, the power manager typically responds by issuing an <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mn-set-power">IRP_MN_SET_POWER</a>. Usually, this IRP will reaffirm the current system state. However, it is possible that drivers might receive an IRP_MN_SET_POWER to the queried state or to some other intermediate state. Drivers should be prepared to handle these situations.

The minidriver specifies this routine's address in the <b>QueryPower</b> member of its <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/ns-ks-_ksdevice_dispatch">KSDEVICE_DISPATCH</a> structure.

This routine is optional.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mn-query-power">IRP_MN_QUERY_POWER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/ns-ks-_ksdevice_dispatch">KSDEVICE_DISPATCH</a>
 

 

