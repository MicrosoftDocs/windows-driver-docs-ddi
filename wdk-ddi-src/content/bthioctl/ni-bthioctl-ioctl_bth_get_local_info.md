---
UID: NI:bthioctl.IOCTL_BTH_GET_LOCAL_INFO
title: IOCTL_BTH_GET_LOCAL_INFO
author: windows-driver-content
description: The IOCTL_BTH_GET_LOCAL_INFO request returns information about the local Bluetooth system and radio.
old-location: bltooth\ioctl_bth_get_local_info.htm
old-project: bltooth
ms.assetid: 0eaee91f-c3d1-4715-9d7a-15dc3935eb36
ms.author: windowsdriverdev
ms.date: 4/27/2018
ms.keywords: IOCTL_BTH_GET_LOCAL_INFO, IOCTL_BTH_GET_LOCAL_INFO control, IOCTL_BTH_GET_LOCAL_INFO control code [Bluetooth Devices], bltooth.ioctl_bth_get_local_info, bth_ioctls_930c11ef-ff69-4044-a4ae-6ea3802a5132.xml, bthioctl/IOCTL_BTH_GET_LOCAL_INFO
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
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
req.irql: "<= PASSIVE_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Bthioctl.h
api_name:
-	IOCTL_BTH_GET_LOCAL_INFO
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_BTH_GET_LOCAL_INFO IOCTL


## -description



The IOCTL_BTH_GET_LOCAL_INFO request returns information about the local Bluetooth system and
     radio.




## -ioctlparameters




### -input-buffer

The 
      <b>AssociatedIrp.SystemBuffer</b> member points to a buffer for a 
      <a href="https://msdn.microsoft.com/library/windows/hardware/ff536644">BTH_LOCAL_RADIO_INFO</a> structure.


### -input-buffer-length

The length of a 
      <a href="https://msdn.microsoft.com/library/windows/hardware/ff536644">BTH_LOCAL_RADIO_INFO</a> structure.


### -output-buffer

The 
      <b>AssociatedIrp.SystemBuffer</b> member points to a buffer that holds a 
      <a href="https://msdn.microsoft.com/library/windows/hardware/ff536644">BTH_LOCAL_RADIO_INFO</a> structure. The
      buffer contains information about the local radio, including a 
      <a href="http://go.microsoft.com/fwlink/p/?linkid=50713">BTH_DEVICE_INFO</a> structure and a 
      <a href="https://msdn.microsoft.com/library/windows/hardware/ff536646">BTH_RADIO_INFO</a> structure.


### -output-buffer-length

The length of a 
      <a href="https://msdn.microsoft.com/library/windows/hardware/ff536644">BTH_LOCAL_RADIO_INFO</a> structure.


### -in-out-buffer








### -inout-buffer-length








### -status-block

The 
      <b>Information</b> member of the STATUS_BLOCK structure is set to the size, in bytes, of the output
      buffer.

The 
      <b>Status</b> member of the STATUS_BLOCK structure is always set to STATUS_SUCCESS.


## -see-also




<a href="http://go.microsoft.com/fwlink/p/?linkid=50713">BTH_DEVICE_INFO</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536644">BTH_LOCAL_RADIO_INFO</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536646">BTH_RADIO_INFO</a>
 

 

