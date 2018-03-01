---
UID: NE:ehstorioctl._PDO_TYPE
title: "_PDO_TYPE"
author: windows-driver-content
description: This enumeration describes the types of Physical Device Objects (PDOs).
old-location: storage\pdo_type.htm
old-project: storage
ms.assetid: 9695d55c-a214-4bba-aba9-38dfa7f54ec9
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: PDO_TYPE, PDO_TYPE enumeration [Storage Devices], PDO_TYPE_CONTROL, PDO_TYPE_DISK, PDO_TYPE_SILO, PDO_TYPE_THIS, PDO_TYPE_UNDEFINED, _PDO_TYPE, ehstorioctl/PDO_TYPE, ehstorioctl/PDO_TYPE_CONTROL, ehstorioctl/PDO_TYPE_DISK, ehstorioctl/PDO_TYPE_SILO, ehstorioctl/PDO_TYPE_THIS, ehstorioctl/PDO_TYPE_UNDEFINED, storage.pdo_type, structs-silo_9ef418bc-5275-4fcf-a49b-804ace353da8.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: ehstorioctl.h
req.include-header: EhStorIoctl.h
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	EhStorIoctl.h
api_name:
-	PDO_TYPE
product: Windows
targetos: Windows
req.typenames: PDO_TYPE
---

# _PDO_TYPE enumeration


## -description


This enumeration describes the types of Physical Device Objects (PDOs).


## -syntax


````
typedef enum _PDO_TYPE { 
  PDO_TYPE_UNDEFINED  = 0,
  PDO_TYPE_DISK       = 1,
  PDO_TYPE_CONTROL    = 2,
  PDO_TYPE_SILO       = 3,
  PDO_TYPE_THIS       = 256
} PDO_TYPE;
````


## -enum-fields




### -field PDO_TYPE_UNDEFINED

Types either enumerated or provided as filter parameter to <a href="..\ehstorioctl\ni-ehstorioctl-ioctl_ehstor_device_enumerate_pdos.md">IOCTL_EHSTOR_DEVICE_ENUMERATE_PDOS</a>



### -field PDO_TYPE_DISK

This value indicates the PDO is for a logical disk device.


### -field PDO_TYPE_CONTROL

This value indicates the PDO is for a logical control device.


### -field PDO_TYPE_SILO

This value indicates the PDO is for a logical silo device.


### -field PDO_TYPE_THIS


## -see-also

<a href="..\ehstorioctl\ni-ehstorioctl-ioctl_ehstor_device_enumerate_pdos.md">IOCTL_EHSTOR_DEVICE_ENUMERATE_PDOS</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20PDO_TYPE enumeration%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

