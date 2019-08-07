---
UID: NI:bthioctl.IOCTL_INTERNAL_BTHENUM_GET_ENUMINFO
title: IOCTL_INTERNAL_BTHENUM_GET_ENUMINFO (bthioctl.h)
description: The IOCTL_INTERNAL_BTHENUM_GET_ENUMINFO request obtains information about the underlying device and service that caused the Plug and Play (PnP) manager to load the profile driver.
old-location: bltooth\ioctl_internal_bthenum_get_enuminfo.htm
tech.root: bltooth
ms.assetid: 43cd8e6b-5710-4308-a7c4-fb6f14940977
ms.date: 04/27/2018
ms.keywords: IOCTL_INTERNAL_BTHENUM_GET_ENUMINFO, IOCTL_INTERNAL_BTHENUM_GET_ENUMINFO control, IOCTL_INTERNAL_BTHENUM_GET_ENUMINFO control code [Bluetooth Devices], bltooth.ioctl_internal_bthenum_get_enuminfo, bth_ioctls_110043d4-a637-4e7a-91d4-fd15a4c39a05.xml, bthioctl/IOCTL_INTERNAL_BTHENUM_GET_ENUMINFO
ms.topic: ioctl
f1_keywords:
 - "bthioctl/IOCTL_INTERNAL_BTHENUM_GET_ENUMINFO"
req.header: bthioctl.h
req.include-header: Bthioctl.h
req.target-type: Windows
req.target-min-winverclnt: Versions:\_Supported in Windows Vista, and later.
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
req.irql: <= PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- Bthioctl.h
api_name:
- IOCTL_INTERNAL_BTHENUM_GET_ENUMINFO
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_INTERNAL_BTHENUM_GET_ENUMINFO IOCTL


## -description



The IOCTL_INTERNAL_BTHENUM_GET_ENUMINFO request obtains information about the underlying device and
     service that caused the Plug and Play (PnP) manager to load the profile driver.




## -ioctlparameters




### -input-buffer

None.


### -input-buffer-length

None.


### -output-buffer

The 
      <b>AssociatedIrp.SystemBuffer</b> member points to a buffer that holds a 
      <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/bthddi/ns-bthddi-_bth_enumerator_info">BTH_ENUMERATOR_INFO</a> structure that
      contains information about the enumeration's type and action, as well as information about the remote
      device.


### -output-buffer-length

The length of a 
      <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/bthddi/ns-bthddi-_bth_enumerator_info">BTH_ENUMERATOR_INFO</a> structure.


### -in-out-buffer








### -inout-buffer-length








### -status-block

<b>Irp->IoStatus.Status</b> is set to STATUS_SUCCESS if the request is successful. Otherwise, <b>Status</b> to the appropriate error condition as a <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values">NTSTATUS</a> code. 


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/bthddi/ns-bthddi-_bth_enumerator_info">BTH_ENUMERATOR_INFO</a>
 

 

