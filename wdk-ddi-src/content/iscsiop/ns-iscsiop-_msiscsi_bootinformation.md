---
UID: NS:iscsiop._MSiSCSI_BootInformation
title: _MSiSCSI_BootInformation (iscsiop.h)
description: The MSiSCSI_BootInformation structure is used with the MSiSCSI_BootInformation WMI Class to expose information about the node that contains the target boot device.
old-location: storage\msiscsi_bootinformation.htm
tech.root: storage
ms.date: 03/29/2018
keywords: ["MSiSCSI_BootInformation structure"]
ms.keywords: "*PMSiSCSI_BootInformation, MSiSCSI_BootInformation, MSiSCSI_BootInformation structure [Storage Devices], PMSiSCSI_BootInformation, PMSiSCSI_BootInformation structure pointer [Storage Devices], _MSiSCSI_BootInformation, iscsiop/MSiSCSI_BootInformation, iscsiop/PMSiSCSI_BootInformation, storage.msiscsi_bootinformation, structs-iSCSI_a33678de-f559-4c7a-8007-55ab0381b613.xml"
req.header: iscsiop.h
req.include-header: Iscsiop.h
req.target-type: Windows
req.target-min-winverclnt: 
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
targetos: Windows
req.typenames: MSiSCSI_BootInformation, *PMSiSCSI_BootInformation
f1_keywords:
 - _MSiSCSI_BootInformation
 - iscsiop/_MSiSCSI_BootInformation
 - PMSiSCSI_BootInformation
 - iscsiop/PMSiSCSI_BootInformation
 - MSiSCSI_BootInformation
 - iscsiop/MSiSCSI_BootInformation
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - iscsiop.h
api_name:
 - MSiSCSI_BootInformation
---

# _MSiSCSI_BootInformation structure


## -description

The MSiSCSI_BootInformation structure is used with the <a href="/windows-hardware/drivers/storage/msiscsi-bootinformation-wmi-class">MSiSCSI_BootInformation WMI Class</a> to expose information about the node that contains the target boot device.

## -struct-fields

### -field NodeName

The name of the initiator node that contains the boot device.

### -field SharedSecretLength

The length, in bytes, of the shared secret for the initiator node.

### -field SharedSecret

The shared secret for the initiator node.

## -remarks

You must implement this class if the adapter supports iSCSI boot.

## -see-also

<a href="/windows-hardware/drivers/storage/msiscsi-bootinformation-wmi-class">MSiSCSI_BootInformationWMI Class</a>
