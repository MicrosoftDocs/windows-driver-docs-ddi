---
UID: NS:ehstorioctl._ENUM_PDO_ENTRY
title: "_ENUM_PDO_ENTRY"
author: windows-driver-content
description: This structure describes a single entry in a result set of Physical Device Objects (PDOs) that are enumerated with IOCTL_EHSTOR_DEVICE_ENUMERATE_PDOS.
old-location: storage\enum_pdo_entry.htm
old-project: storage
ms.assetid: c3f5cc8e-a600-4ca1-8745-d74943feb2c7
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: ENUM_PDO_ENTRY structure [Storage Devices], PENUM_PDO_ENTRY structure pointer [Storage Devices], ehstorioctl/ENUM_PDO_ENTRY, storage.enum_pdo_entry, ENUM_PDO_ENTRY, PENUM_PDO_ENTRY, structs-silo_8303b6a6-8f4f-4f0c-91ce-9d70ea72f4f2.xml, ehstorioctl/PENUM_PDO_ENTRY, _ENUM_PDO_ENTRY, *PENUM_PDO_ENTRY
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	EhStorIoctl.h
apiname:
-	ENUM_PDO_ENTRY
product: Windows
targetos: Windows
req.typenames: ENUM_PDO_ENTRY, *PENUM_PDO_ENTRY
---

# _ENUM_PDO_ENTRY structure


## -description


This structure describes a single entry in a result set of Physical Device Objects (PDOs) that are enumerated with <a href="..\ehstorioctl\ni-ehstorioctl-ioctl_ehstor_device_enumerate_pdos.md">IOCTL_EHSTOR_DEVICE_ENUMERATE_PDOS</a>.


## -syntax


````
typedef struct _ENUM_PDO_ENTRY {
  UCHAR type;
  UCHAR state;
  UCHAR capabilities;
  ULONG ulSTID;
  UCHAR bSpecificationMajor;
  UCHAR bSpecificationMinor;
  UCHAR bImplementationMajor;
  UCHAR bImplementationMinor;
  WCHAR wszDeviceInstancePath[(2 * MAX_PATH) + 1];
} ENUM_PDO_ENTRY, *PENUM_PDO_ENTRY;
````


## -struct-fields




### -field type

This member indicates the type of the PDO that is being identified, as defined by PDO_TYPE.


### -field state

This member contains information about the current PnP state of the PDO, as defined by PDO_STATE.


### -field capabilities

This member contains a bitmask with bits indicating information about the silo represented by the PDO in question, as defined by PDO_CAPS.


### -field ulSTID

This member contains the silo type identifier, as defined and assigned by the IEEE 1667 working group.


### -field bSpecificationMajor



### -field bSpecificationMinor



### -field bImplementationMajor



### -field bImplementationMinor



### -field wszDeviceInstancePath

The string contained in this member is the device instance path in a form suitable for use with the Win32 API CreateFile routine.


## -see-also

<a href="..\ehstorioctl\ni-ehstorioctl-ioctl_ehstor_device_enumerate_pdos.md">IOCTL_EHSTOR_DEVICE_ENUMERATE_PDOS</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20ENUM_PDO_ENTRY structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

