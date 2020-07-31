---
UID: NC:ks.PFNKSDEVICEPNPSTART
title: PFNKSDEVICEPNPSTART (ks.h)
description: An AVStream minidriver's AVStrMiniDeviceStart routine is called when an IRP_MN_START_DEVICE request is sent for a specified device.
old-location: stream\avstrminidevicestart.htm
tech.root: stream
ms.assetid: 5a09a8b1-7a20-42e3-a58d-ecd4e7a0558e
ms.date: 04/23/2018
keywords: ["PFNKSDEVICEPNPSTART callback function"]
ms.keywords: AVStrMiniDeviceStart, AVStrMiniDeviceStart routine [Streaming Media Devices], PFNKSDEVICEPNPSTART, avstclbk_b9fd90e7-3d9b-47a3-86c4-8df35f000269.xml, ks/AVStrMiniDeviceStart, stream.avstrminidevicestart
f1_keywords:
 - "ks/AVStrMiniDeviceStart"
 - "AVStrMiniDeviceStart"
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
- AVStrMiniDeviceStart
targetos: Windows
req.typenames: 
---

# PFNKSDEVICEPNPSTART callback function


## -description


An AVStream minidriver's <i>AVStrMiniDeviceStart</i> routine is called when an <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mn-start-device">IRP_MN_START_DEVICE</a> request is sent for a specified device.


## -parameters




### -param Device [in]

Pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-_ksdevice">KSDEVICE</a> structure describing the device to be started.


### -param Irp [in]

Pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mn-start-device">IRP_MN_START_DEVICE</a> that was received.


### -param TranslatedResourceList [in, optional]

Pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_cm_resource_list">CM_RESOURCE_LIST</a> structure that contains the translated resource list extracted from <i>Irp</i>. Equals <b>NULL</b> if <i>Device</i> has no assigned resources. Optional.


### -param UntranslatedResourceList [in, optional]

Pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_cm_resource_list">CM_RESOURCE_LIST</a> structure that contains the untranslated resource list extracted from <i>Irp</i>. Equals <b>NULL</b> if the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-_ksdevice">KSDEVICE</a> member of this parameter list has no assigned resources. Optional.


## -returns



Should return STATUS_SUCCESS or the error code that was returned from the attempt to perform the operation. The start is guaranteed to succeed if the routine returns a successful status code. Do NOT return STATUS_PENDING.




## -remarks



Specify this routine's address in the <b>Start</b> member of its <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-_ksdevice_dispatch">KSDEVICE_DISPATCH</a> structure.

Typically, this routine is used by minidrivers that must evaluate assigned resources. Resource lists are extracted from <i>Irp</i> for the convenience of the minidriver. A minidriver can parse the resource list to find the interrupt assigned to the device, as well as the physical address of memory resources.

Minidrivers may use this routine to allocate context information to associate with the AVStream device. (This is similar to a minidriver under stream class using the device extension to store context information.)

Note that STATUS_PENDING is not a legal return code from this function.  To perform actions in the context of a worker thread before AVStream has completed start actions such as enabling device interfaces, use a post start dispatch. See <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nc-ks-pfnksdevice">AVStrMiniDevicePostStart</a>.

This routine is optional.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_cm_resource_list">CM_RESOURCE_LIST</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-_ksdevice_dispatch">KSDEVICE_DISPATCH</a>
 

 

