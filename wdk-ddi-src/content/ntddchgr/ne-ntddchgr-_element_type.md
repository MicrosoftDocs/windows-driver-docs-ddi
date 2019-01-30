---
UID: NE:ntddchgr._ELEMENT_TYPE
title: "_ELEMENT_TYPE" (ntddchgr.h)
description: The ELEMENT_TYPE enumeration provides a list of changer element types defined by the SCSI-3 specification.
old-location: storage\element_type.htm
tech.root: storage
ms.assetid: 909e0645-3824-40ff-bec9-128a9939eb1e
ms.date: 03/29/2018
ms.keywords: "*PELEMENT_TYPE, AllElements, ChangerDoor, ChangerDrive, ChangerIEPort, ChangerKeypad, ChangerMaxElement, ChangerSlot, ChangerTransport, ELEMENT_TYPE, ELEMENT_TYPE enumeration [Storage Devices], PELEMENT_TYPE, PELEMENT_TYPE enumeration pointer [Storage Devices], _ELEMENT_TYPE, ntddchgr/AllElements, ntddchgr/ChangerDoor, ntddchgr/ChangerDrive, ntddchgr/ChangerIEPort, ntddchgr/ChangerKeypad, ntddchgr/ChangerMaxElement, ntddchgr/ChangerSlot, ntddchgr/ChangerTransport, ntddchgr/ELEMENT_TYPE, ntddchgr/PELEMENT_TYPE, storage.element_type, structs-changer_e97997e8-4dc3-46e9-897e-3ded47adf8b8.xml"
ms.topic: enum
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
-	ELEMENT_TYPE
product:
- Windows
targetos: Windows
req.typenames: ELEMENT_TYPE, *PELEMENT_TYPE
---

# _ELEMENT_TYPE enumeration


## -description


The ELEMENT_TYPE enumeration provides a list of changer element types defined by the <i>SCSI-3</i> specification. 


## -enum-fields




### -field AllElements

Indicates all elements of a changer, including its robotic transport, drives, slots, and IEport. <b>AllElements</b> is valid only in a <a href="https://msdn.microsoft.com/library/windows/hardware/ff551424">ChangerGetElementStatus</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff551433">ChangerInitializeElementStatus</a> call.


### -field ChangerTransport

Indicates the changer's robotic transport element, which is used to move media between IEports, slots, and drives.


### -field ChangerSlot

Indicates a storage element, which is a slot in the changer in which media is stored when not mounted in a drive.


### -field ChangerIEPort

Indicates an import/export element (IEport), which is a single or multiple-cartridge access port in some changers. An element is an IEport only if it is possible to move a piece of media from a slot to the IEport.


### -field ChangerDrive

Indicates a data transfer element where data can be read from and written to media. 


### -field ChangerDoor

Indicates a mechanism that provides access to all media in a changer at one time (as compared to an IEport that provides access to one or more, but not all, media). For example, a large front door or a magazine that contains all media in the changer are elements of this type. <b>ChangerDoor</b> is valid only in a <a href="https://msdn.microsoft.com/library/windows/hardware/ff551447">ChangerSetAccess</a> call.


### -field ChangerKeypad

Indicates the keypad or other input control on the front panel of a changer. <b>ChangerKeypad</b> is valid only in a <a href="https://msdn.microsoft.com/library/windows/hardware/ff551447">ChangerSetAccess</a> call.


### -field ChangerMaxElement

Indicates the upper limit of the enumerators in this enumeration. 


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff551424">ChangerGetElementStatus</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551433">ChangerInitializeElementStatus</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551447">ChangerSetAccess</a>
 

 

