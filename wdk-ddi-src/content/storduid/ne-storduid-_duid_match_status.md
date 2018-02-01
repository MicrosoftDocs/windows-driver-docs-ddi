---
UID: NE:storduid._DUID_MATCH_STATUS
title: "_DUID_MATCH_STATUS"
author: windows-driver-content
description: The DUID_MATCH_STATUS enumeration lists the status values that the CompareStorageDuids routine returns.
old-location: storage\duid_match_status.htm
old-project: storage
ms.assetid: 61a60e77-387c-42d6-b56b-694ce0c86570
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: storduid/DuidErrorMaximum, DuidNoMatch, storduid/DuidExactMatch, storduid/DuidNoMatch, storduid/DuidErrorGeneral, storduid/DuidSubIdMatch, storduid/DuidErrorInvalidDeviceIdDescSize, storduid/DuidErrorInvalidDuid, _DUID_MATCH_STATUS, DuidErrorInvalidDeviceDescSize, DuidErrorInvalidDuid, storage.duid_match_status, DUID_MATCH_STATUS enumeration [Storage Devices], DuidSubIdMatch, DuidErrorInvalidDeviceIdDescSize, DuidErrorVersionMismatch, DuidErrorGeneral, DuidExactMatch, storduid/DuidErrorMissingDuid, storduid/DuidErrorInvalidDeviceDescSize, structs-general_8e33f54f-7115-42c2-aa06-112c79f9c392.xml, storduid/DuidErrorVersionMismatch, DuidErrorInvalidLayoutSigVersion, DuidErrorMissingDuid, DuidErrorMaximum, DuidErrorInvalidLayoutSigSize, storduid/DuidErrorInvalidLayoutSigVersion, storduid/DUID_MATCH_STATUS, storduid/DuidErrorInvalidLayoutSigSize, DUID_MATCH_STATUS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: storduid.h
req.include-header: Storduid.h
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
-	storduid.h
apiname:
-	DUID_MATCH_STATUS
product: Windows
targetos: Windows
req.typenames: DUID_MATCH_STATUS
req.product: Windows 10 or later.
---

# _DUID_MATCH_STATUS enumeration


## -description


The DUID_MATCH_STATUS enumeration lists the status values that the <a href="..\storduid\nf-storduid-comparestorageduids.md">CompareStorageDuids</a> routine returns.


## -syntax


````
typedef enum _DUID_MATCH_STATUS { 
  DuidExactMatch                    = 0,
  DuidSubIdMatch                    = 1,
  DuidNoMatch                       = 2,
  DuidErrorGeneral                  = 100,
  DuidErrorMissingDuid              = 101,
  DuidErrorVersionMismatch          = 102,
  DuidErrorInvalidDuid              = 103,
  DuidErrorInvalidDeviceIdDescSize  = 104,
  DuidErrorInvalidDeviceDescSize    = 105,
  DuidErrorInvalidLayoutSigSize     = 106,
  DuidErrorInvalidLayoutSigVersion  = 107,
  DuidErrorMaximum                  = 108
} DUID_MATCH_STATUS;
````


## -enum-fields




### -field DuidExactMatch

All fields in the two Device Unique Identifiers (DUIDs) match exactly.


### -field DuidSubIdMatch

Either the serial number or one of the unique sub-IDs matches. The two DUIDs probably represent the same device.


### -field DuidNoMatch

None of the sub-IDs match in page 83h of the vital product data (VPD). None of the non-VPD data matches.


### -field DuidErrorGeneral

An error occurred for an unspecified cause.


### -field DuidErrorMissingDuid

One of the two DUIDs to compare is missing.


### -field DuidErrorVersionMismatch

The two DUIDs to compare do not have the same version.


### -field DuidErrorInvalidDuid

At least one of the two DUIDs to compare is invalid.


### -field DuidErrorInvalidDeviceIdDescSize

At least one of the two DUIDs to compare contains an invalid device ID descriptor (<a href="..\ntddstor\ns-ntddstor-_storage_device_id_descriptor.md">STORAGE_DEVICE_ID_DESCRIPTOR</a>). This descriptor reports VPD data.


### -field DuidErrorInvalidDeviceDescSize

At least one of the two DUIDs to compare contains an invalid device descriptor (<a href="..\ntddstor\ns-ntddstor-_storage_device_descriptor.md">STORAGE_DEVICE_DESCRIPTOR</a>). This descriptor reports non-VPD inquiry data..


### -field DuidErrorInvalidLayoutSigSize

At least one of the two DUIDs to compare contains an invalid drive layout signature size.


### -field DuidErrorInvalidLayoutSigVersion

At least one of the two DUIDs to compare contains an invalid drive layout signature.


### -field DuidErrorMaximum

This value delimits the upper limit of the enumeration values in this enumeration. This value allows a DUID consumer to create a loop that tests for all valid error values that the <a href="..\storduid\nf-storduid-comparestorageduids.md">CompareStorageDuids</a> routine returns. As new identifier data is added to future versions of the DUID, new error values will specify which parts of the DUID are not well-formed.


## -see-also

<a href="..\ntddstor\ns-ntddstor-_storage_device_descriptor.md">STORAGE_DEVICE_DESCRIPTOR</a>

<a href="..\ntddstor\ns-ntddstor-_storage_device_id_descriptor.md">STORAGE_DEVICE_ID_DESCRIPTOR</a>

<a href="..\storduid\nf-storduid-comparestorageduids.md">CompareStorageDuids</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20DUID_MATCH_STATUS enumeration%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

