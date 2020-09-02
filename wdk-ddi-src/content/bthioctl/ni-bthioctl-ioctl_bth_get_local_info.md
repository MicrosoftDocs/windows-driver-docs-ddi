---
UID: NI:bthioctl.IOCTL_BTH_GET_LOCAL_INFO
title: IOCTL_BTH_GET_LOCAL_INFO (bthioctl.h)
description: The IOCTL_BTH_GET_LOCAL_INFO request returns information about the local Bluetooth system and radio.
old-location: bltooth\ioctl_bth_get_local_info.htm
tech.root: bltooth
ms.assetid: 0eaee91f-c3d1-4715-9d7a-15dc3935eb36
ms.date: 04/27/2018
keywords: ["IOCTL_BTH_GET_LOCAL_INFO IOCTL"]
ms.keywords: IOCTL_BTH_GET_LOCAL_INFO, IOCTL_BTH_GET_LOCAL_INFO control, IOCTL_BTH_GET_LOCAL_INFO control code [Bluetooth Devices], bltooth.ioctl_bth_get_local_info, bth_ioctls_930c11ef-ff69-4044-a4ae-6ea3802a5132.xml, bthioctl/IOCTL_BTH_GET_LOCAL_INFO
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
targetos: Windows
req.typenames: 
f1_keywords:
 - IOCTL_BTH_GET_LOCAL_INFO
 - bthioctl/IOCTL_BTH_GET_LOCAL_INFO
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Bthioctl.h
api_name:
 - IOCTL_BTH_GET_LOCAL_INFO
---

# IOCTL_BTH_GET_LOCAL_INFO IOCTL


## -description

The IOCTL_BTH_GET_LOCAL_INFO request returns information about the local Bluetooth system and
     radio.

## -ioctlparameters

### -input-buffer

The 
      <b>AssociatedIrp.SystemBuffer</b> member points to a buffer for a 
      <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bthioctl/ns-bthioctl-_bth_local_radio_info">BTH_LOCAL_RADIO_INFO</a> structure.

### -input-buffer-length

The length of a 
      <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bthioctl/ns-bthioctl-_bth_local_radio_info">BTH_LOCAL_RADIO_INFO</a> structure.

### -output-buffer

The 
      <b>AssociatedIrp.SystemBuffer</b> member points to a buffer that holds a 
      <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bthioctl/ns-bthioctl-_bth_local_radio_info">BTH_LOCAL_RADIO_INFO</a> structure. The
      buffer contains information about the local radio, including a 
      <a href="https://go.microsoft.com/fwlink/p/?linkid=50713">BTH_DEVICE_INFO</a> structure and a 
      <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bthioctl/ns-bthioctl-_bth_radio_info">BTH_RADIO_INFO</a> structure.

### -output-buffer-length

The length of a 
      <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bthioctl/ns-bthioctl-_bth_local_radio_info">BTH_LOCAL_RADIO_INFO</a> structure.

### -in-out-buffer

### -inout-buffer-length

### -status-block

The 
      <b>Information</b> member of the STATUS_BLOCK structure is set to the size, in bytes, of the output
      buffer.

The 
      <b>Status</b> member of the STATUS_BLOCK structure is always set to STATUS_SUCCESS.

## -see-also

<a href="https://go.microsoft.com/fwlink/p/?linkid=50713">BTH_DEVICE_INFO</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bthioctl/ns-bthioctl-_bth_local_radio_info">BTH_LOCAL_RADIO_INFO</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bthioctl/ns-bthioctl-_bth_radio_info">BTH_RADIO_INFO</a>

