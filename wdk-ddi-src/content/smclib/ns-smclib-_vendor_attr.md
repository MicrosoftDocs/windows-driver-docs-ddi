---
UID: NS:smclib._VENDOR_ATTR
title: "_VENDOR_ATTR"
author: windows-driver-content
description: The VENDOR_ATTR structure defines the data that is stored in the VendorAttr member of the SMARTCARD_EXTENSION structure. VENDOR_ATTR also holds information that identifies the smart card reader, such as the vendor name, unit number, and serial number.
old-location: smartcrd\vendor_attr.htm
old-project: smartcrd
ms.assetid: f166ced5-2d63-4e35-af77-78ca80c888d7
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: smartcrd.vendor_attr, *PVENDOR_ATTR, PVENDOR_ATTR, _VENDOR_ATTR, smclib/VENDOR_ATTR, VENDOR_ATTR, VENDOR_ATTR structure [Smart Card Reader Devices], scstruct_dfa4be20-d572-46d6-aff7-c4c16d930c7f.xml, smclib/PVENDOR_ATTR, PVENDOR_ATTR structure pointer [Smart Card Reader Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: smclib.h
req.include-header: Smclib.h
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
-	smclib.h
apiname:
-	VENDOR_ATTR
product: Windows
targetos: Windows
req.typenames: VENDOR_ATTR, *PVENDOR_ATTR
req.product: Windows 10 or later.
---

# _VENDOR_ATTR structure


## -description


The VENDOR_ATTR structure defines the data that is stored in the <b>VendorAttr</b> member of the <a href="..\smclib\ns-smclib-_smartcard_extension.md">SMARTCARD_EXTENSION</a> structure. VENDOR_ATTR also holds information that identifies the smart card reader, such as the vendor name, unit number, and serial number. 


## -syntax


````
typedef struct _VENDOR_ATTR {
  struct {
    USHORT Length;
    UCHAR  Buffer[MAXIMUM_ATTR_STRING_LENGTH];
  } VendorName;
  struct {
    USHORT Length;
    UCHAR  Buffer[MAXIMUM_ATTR_STRING_LENGTH];
  } IfdType;
  ULONG  UnitNo;
  struct {
    USHORT BuildNumber;
    UCHAR  VersionMinor;
    UCHAR  VersionMajor;
  } IfdVersion;
  struct {
    USHORT Length;
    UCHAR  Buffer[MAXIMUM_ATTR_STRING_LENGTH];
  } IfdSerialNo;
  ULONG  Reserved[25];
} VENDOR_ATTR, *PVENDOR_ATTR;
````


## -struct-fields




### -field VendorName


      A structure with the following members:
      
     


### -field VendorName.Length

Contains the ANSI-coded name of the vendor. Because a length field is provided, no terminating <b>NULL</b> character is necessary. This member is required. 


### -field VendorName.Buffer

Contains the length of the ANSI-coded name of the vendor. This member is required. 


### -field IfdType


      A structure with the following members:
      
     


### -field IfdType.Length

Contains the length of the ANSI-coded designation of the reader. This member is required. 


### -field IfdType.Buffer

Contains the ANSI-coded reader name. This member is required. 



### -field UnitNo

Contains the zero-based number of this unit. Because you can have more than one reader of this kind installed, <b>UnitNo</b> can distinguish the readers. This member is required. 


### -field IfdVersion


      A structure with the following members:
      
     


### -field IfdVersion.BuildNumber

Contains the build number of the reader driver. This member can be used for support purposes and should be maintained only if the reader allows the value to be queried. This member is optional. 


### -field IfdVersion.VersionMinor

Contains the minor version number of the reader driver. This member can be used for support purposes and should be maintained only if the reader allows the value to be queried. This member is optional. 


### -field IfdVersion.VersionMajor

Contains the major version number of the reader driver. This member can be used for support purposes and should be maintained only if the reader allows the value to be queried. This member is optional. 


### -field IfdSerialNo


      A structure with the following members:
      
     


### -field IfdSerialNo.Length

Contains the length of the serial number, in bytes, of the connected reader. 


### -field IfdSerialNo.Buffer

A pointer to the serial number of the connected reader. This field should only be maintained if the reader allows the serial number to be queried. This member is optional. 


### -field Reserved

Reserved for system use. 

