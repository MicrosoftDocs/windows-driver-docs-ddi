---
UID: NE:ntddstor._STORAGE_PROTOCOL_UFS_DATA_TYPE
title: _STORAGE_PROTOCOL_UFS_DATA_TYPE
author: windows-driver-content
description: The UFS (Universal Flash Storage) data type. Describes the type of UFS specific data that's to be queried during an IOCTL_STORAGE_QUERY_PROPERTY request.
old-location: storage\storage_protocol_ufs_data_type.htm
old-project: storage
ms.assetid: A4324FAD-A925-4D65-9697-9CC2878DBE0B
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: ntddstor/ UfsDataTypeQueryDescriptor, ntddstor/ UfsDataTypeMax, UfsDataTypeMax, *PSTORAGE_PROTOCOL_UFS_DATA_TYPE, UfsDataTypeUnknown, STORAGE_PROTOCOL_UFS_DATA_TYPE, _STORAGE_PROTOCOL_UFS_DATA_TYPE, UfsDataTypeQueryDescriptor, storage.storage_protocol_ufs_data_type, ntddstor/STORAGE_PROTOCOL_UFS_DATA_TYPE, STORAGE_PROTOCOL_UFS_DATA_TYPE enumeration [Storage Devices], ntddstor/UfsDataTypeUnknown
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
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
-	Ntddstor.h
apiname: 
-	STORAGE_PROTOCOL_UFS_DATA_TYPE
product: Windows
targetos: Windows
req.typenames: STORAGE_PROTOCOL_UFS_DATA_TYPE, *PSTORAGE_PROTOCOL_UFS_DATA_TYPE
---

# _STORAGE_PROTOCOL_UFS_DATA_TYPE enumeration


## -description


The UFS (Universal Flash Storage) data type. Describes the type of UFS specific data that's to be queried during an <a href="https://msdn.microsoft.com/library/windows/hardware/ff560590">IOCTL_STORAGE_QUERY_PROPERTY</a> request.


## -syntax


````
typedef enum _STORAGE_PROTOCOL_UFS_DATA_TYPE { 
  UfsDataTypeUnknown              = 0,
      UfsDataTypeQueryDescriptor,
          UfsDataTypeMax
} STORAGE_PROTOCOL_UFS_DATA_TYPE;
````


## -enum-fields




### -field UfsDataTypeUnknown

Unknown data type.


### -field UfsDataTypeQueryDescriptor

Query Descriptor data type. Retrieved by command UfsSrbQueryProtocolQueryDescriptor.


### -field UfsDataTypeMax

Max size of data type.


## -see-also

<a href="..\ntddstor\ns-ntddstor-_storage_protocol_data_descriptor.md">STORAGE_PROTOCOL_DATA_DESCRIPTOR</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20STORAGE_PROTOCOL_UFS_DATA_TYPE enumeration%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

