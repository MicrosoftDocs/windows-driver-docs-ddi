---
UID: NS:ntddchgr._CHANGER_ELEMENT
title: "_CHANGER_ELEMENT"
author: windows-driver-content
description: The CHANGER_ELEMENT structure contains a description of a changer element.
old-location: storage\changer_element.htm
old-project: storage
ms.assetid: 85035147-0ae8-482a-9a12-1e4e53ae1969
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PCHANGER_ELEMENT, CHANGER_ELEMENT, CHANGER_ELEMENT structure [Storage Devices], PCHANGER_ELEMENT, PCHANGER_ELEMENT structure pointer [Storage Devices], _CHANGER_ELEMENT, ntddchgr/CHANGER_ELEMENT, ntddchgr/PCHANGER_ELEMENT, storage.changer_element, structs-changer_b1685d99-20ff-495d-a9e3-c63571559106.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddchgr.h
req.include-header: 
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
-	ntddchgr.h
api_name:
-	CHANGER_ELEMENT
product: Windows
targetos: Windows
req.typenames: CHANGER_ELEMENT, *PCHANGER_ELEMENT
---

# _CHANGER_ELEMENT structure


## -description


The CHANGER_ELEMENT structure contains a description of a changer element. 


## -struct-fields




### -field ElementType

Indicates the type of element. Can be one of the following values taken from the <a href="https://msdn.microsoft.com/library/windows/hardware/ff553754">ELEMENT_TYPE</a> enumeration.





#### AllElements

All elements of a changer, including its robotic transport, drives, slots, and IEport. <b>AllElements</b> is valid only in a <b>ChangerGetElementStatus</b> or <b>ChangerInitializeElementStatus</b> call.





#### ChangerTransport

The changer's robotic transport element, which is used to move media between IEports, slots, and drives.





#### ChangerSlot

A storage element, which is a slot in the changer in which media is stored when not mounted in a drive.





#### ChangerIEPort

An import/export element (IEport), which is a single or multiple-cartridge access port in some changers. An element is an IEport only if it is possible to move a piece of media from a slot to the IEport.





#### ChangerDrive

A data transfer element where data can be read from and written to media. 





#### ChangerDoor

A mechanism that provides access to all media in a changer at one time (as compared to an IEport that provides access to one or more, but not all, media). For example, a large front door or a magazine that contains all media in the changer are elements of this type. <b>ChangerDoor</b> is valid only in a <b>ChangerSetAccess</b> call.





#### ChangerKeypad

The keypad or other input control on the front panel of a changer. <b>ChangerKeypad</b> is valid only in a <b>ChangerSetAccess</b> call.


### -field ElementAddress

Indicates the element's zero-based address used by the system. A changer miniclass driver is responsible for translating this address to the device-specific address used by the changer.


## -remarks



CHANGER_ELEMENT is used by both the changer class driver and a changer miniclass driver to describe a changer element. 

On input, a changer miniclass driver must translate the zero-based address in <b>ElementAddress</b> to a device-specific address before accessing the element. On output, the driver must translate a device-specific address to the zero-based equivalent before filling in <b>ElementAddress</b>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff551459">CHANGER_ELEMENT_LIST</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551461">CHANGER_ELEMENT_STATUS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553754">ELEMENT_TYPE</a>
 

 

