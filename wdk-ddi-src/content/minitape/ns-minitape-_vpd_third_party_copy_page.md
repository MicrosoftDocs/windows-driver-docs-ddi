---
UID: NS:minitape._VPD_THIRD_PARTY_COPY_PAGE
title: _VPD_THIRD_PARTY_COPY_PAGE (minitape.h)
description: The VPD_THIRD_PARTY_COPY_PAGE structure defines the vital product data (VPD) page for offload data transfer operations.
old-location: storage\vpd_third_party_copy_page.htm
tech.root: storage
ms.assetid: E8D9E05C-26C3-474C-854F-9AD12C8834DF
ms.date: 03/29/2018
ms.keywords: "*PVPD_THIRD_PARTY_COPY_PAGE, PVPD_THIRD_PARTY_COPY_PAGE, PVPD_THIRD_PARTY_COPY_PAGE structure pointer [Storage Devices], VPD_THIRD_PARTY_COPY_PAGE, VPD_THIRD_PARTY_COPY_PAGE structure [Storage Devices], _VPD_THIRD_PARTY_COPY_PAGE, scsi/PVPD_THIRD_PARTY_COPY_PAGE, scsi/VPD_THIRD_PARTY_COPY_PAGE, storage.vpd_third_party_copy_page"
f1_keywords:
 - "minitape/VPD_THIRD_PARTY_COPY_PAGE"
req.header: minitape.h
req.include-header: Scsi.h, Minitape.h, Storport.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with Windows 8.
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
- HeaderDef
api_location:
- scsi.h
api_name:
- VPD_THIRD_PARTY_COPY_PAGE
product:
- Windows
targetos: Windows
req.typenames: VPD_THIRD_PARTY_COPY_PAGE, *PVPD_THIRD_PARTY_COPY_PAGE
---

# _VPD_THIRD_PARTY_COPY_PAGE structure


## -description


The <b>VPD_THIRD_PARTY_COPY_PAGE</b> structure defines the vital product data (VPD) page for offload data transfer operations.


## -struct-fields




### -field DeviceType

The device type. This is the same device type defined for use in the inquiry data for the storage device.


### -field DeviceTypeQualifier

A qualifier code for the device. Currently, <b>DEVICE_CONNECTED</b>, is the only valid value.


### -field PageCode

The page code for the VPD third party copy page. This page code is defined as 0x8f.


### -field PageLength

The length, in bytes, of the VPD page. For offload data transfer on Windows, <b>PageLength</b> must be >= 0x24.


### -field ThirdPartyCopyDescriptors

Support descriptors for copy operations. On Windows systems, <b>ThirdPartyCopyDescriptors</b>  will contain one descriptor formatted as a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/scsi/ns-scsi-_windows_block_device_token_limits_descriptor">WINDOWS_BLOCK_DEVICE_TOKEN_LIMITS_DESCRIPTOR</a> structure.


## -remarks



All multibyte values are in big endian format. Prior to evaluation, these values must be converted to match the endian format of the current platform.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/scsi/ns-scsi-_windows_block_device_token_limits_descriptor">WINDOWS_BLOCK_DEVICE_TOKEN_LIMITS_DESCRIPTOR</a>
 

 

