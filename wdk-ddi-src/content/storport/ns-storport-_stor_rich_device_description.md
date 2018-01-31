---
UID: NS:storport._STOR_RICH_DEVICE_DESCRIPTION
title: "_STOR_RICH_DEVICE_DESCRIPTION"
author: windows-driver-content
description: The STOR_RICH_DEVICE_DESCRIPTION structure describes the attributes of the physical device for which a driver is requesting a DMA (direct memory access) adapter.
old-location: storage\stor_rich_device_description.htm
old-project: storage
ms.assetid: 765A420C-F406-4A46-BDCC-26A451549F8D
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: STOR_RICH_DEVICE_DESCRIPTION, *PSTOR_RICH_DEVICE_DESCRIPTION, PSTOR_RICH_DEVICE_DESCRIPTION, _STOR_RICH_DEVICE_DESCRIPTION, storport/PSTOR_RICH_DEVICE_DESCRIPTION, PSTOR_RICH_DEVICE_DESCRIPTION structure pointer [Storage Devices], storport/STOR_RICH_DEVICE_DESCRIPTION, storage.stor_rich_device_description, STOR_RICH_DEVICE_DESCRIPTION structure [Storage Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: storport.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10, version 1607
req.target-min-winversvr: Windows Server 2016
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
-	Storport.h
apiname:
-	STOR_RICH_DEVICE_DESCRIPTION
product: Windows
targetos: Windows
req.typenames: "*PSTOR_RICH_DEVICE_DESCRIPTION, STOR_RICH_DEVICE_DESCRIPTION"
req.product: Windows 10 or later.
---

# _STOR_RICH_DEVICE_DESCRIPTION structure


## -description


<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]

The <b>STOR_RICH_DEVICE_DESCRIPTION</b> structure describes the attributes of the <b> physical device </b> for which a driver is requesting a DMA (direct memory access) adapter.


## -syntax


````
typedef struct _STOR_RICH_DEVICE_DESCRIPTION {
  ULONG Version;
  ULONG Size;
  Char  VendorId[STOR_VENDOR_ID_LENGTH +1];
  Char  ModelNumber[STOR_MODEL_NUMBER_LENGTH + 1];
  Char  FirmwareRevision[STOR_FIRMWARE_REVISION_LENGTH + 1];
} STOR_RICH_DEVICE_DESCRIPTION, *PSTOR_RICH_DEVICE_DESCRIPTION;
````


## -struct-fields




#### - Version

The version of the structure. Must be STOR_RICH_DEVICE_DESCRIPTION_STRUCTURE_VERSION.


#### - Size

The size of the structure. 


#### - VendorId

A string representing the device’s vendor ID. May be an empty string if ModelNumber is provided.




#### - ModelNumber

A string representing the device’s model.






#### - FirmwareRevision

A string representing the device’s currently active firmware revision.



## -remarks


Miniport can choose to support this UnitControl if the device reports longer Model or Firmware information than defined in SCSI.

This is invoked during the Unit enumeration process or the device description update process. ScsiUnitRichDescription is a caller-allocated version of this structure.



## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/hh920398">HwStorUnitControl</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20STOR_RICH_DEVICE_DESCRIPTION structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

