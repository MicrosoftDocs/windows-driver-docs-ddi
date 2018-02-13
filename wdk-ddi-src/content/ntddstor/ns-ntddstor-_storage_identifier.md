---
UID: NS:ntddstor._STORAGE_IDENTIFIER
title: "_STORAGE_IDENTIFIER"
author: windows-driver-content
description: The STORAGE_IDENTIFIER structure represents a SCSI identification descriptor.
old-location: storage\storage_identifier.htm
old-project: storage
ms.assetid: f2b0610a-dffa-48fb-bc5a-355fa9f05770
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: ntddstor/STORAGE_IDENTIFIER, PSTORAGE_IDENTIFIER, STORAGE_IDENTIFIER, STORAGE_IDENTIFIER structure [Storage Devices], _STORAGE_IDENTIFIER, storage.storage_identifier, ntddstor/PSTORAGE_IDENTIFIER, PSTORAGE_IDENTIFIER structure pointer [Storage Devices], structs-general_29c666d7-3e61-44fe-a36e-979418dbb958.xml, *PSTORAGE_IDENTIFIER
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddstor.h
req.include-header: Ntddstor.h
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ntddstor.h
apiname:
-	STORAGE_IDENTIFIER
product: Windows
targetos: Windows
req.typenames: "*PSTORAGE_IDENTIFIER, STORAGE_IDENTIFIER"
---

# _STORAGE_IDENTIFIER structure


## -description


The STORAGE_IDENTIFIER structure represents a SCSI identification descriptor.


## -syntax


````
typedef struct _STORAGE_IDENTIFIER {
  STORAGE_IDENTIFIER_CODE_SET CodeSet;
  STORAGE_IDENTIFIER_TYPE     Type;
  USHORT                      IdentifierSize;
  USHORT                      NextOffset;
  STORAGE_ASSOCIATION_TYPE    Association;
  UCHAR                       Identifier[1];
} STORAGE_IDENTIFIER, *PSTORAGE_IDENTIFIER;
````


## -struct-fields




### -field CodeSet

Specifies the code set used by a SCSI identification descriptor to identify a logical unit.


### -field Type

Contains an enumerator value of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff566990">STORAGE_IDENTIFIER_TYPE</a> that indicates the identifier type.


### -field IdentifierSize

Specifies the size in bytes of the identifier.


### -field NextOffset

Specifies the offset in bytes from the current descriptor to the next descriptor.


### -field Association

Contains an enumerator value of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff566349">STORAGE_ASSOCIATION_TYPE</a> that indicates whether the descriptor identifies a device or a port.


### -field Identifier

Contains the identifier associated with this descriptor.


## -remarks



Every device identification page (page code 0x83) of SCSI vital product data contains a series of identification descriptors. The STORAGE_IDENTIFIER structure represents a SCSI identification descriptor.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff566990">STORAGE_IDENTIFIER_TYPE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566349">STORAGE_ASSOCIATION_TYPE</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20STORAGE_IDENTIFIER structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

