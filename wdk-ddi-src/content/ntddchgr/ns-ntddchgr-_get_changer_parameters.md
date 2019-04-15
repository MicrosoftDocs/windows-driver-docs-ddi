---
UID: NS:ntddchgr._GET_CHANGER_PARAMETERS
title: _GET_CHANGER_PARAMETERS (ntddchgr.h)
description: Retrieves the characteristics of the changer.
old-location: storage\get_changer_parameters.htm
tech.root: storage
ms.assetid: c9a47406-5dd2-4cda-b241-3a439406ac75
ms.date: 03/29/2018
ms.keywords: "*PGET_CHANGER_PARAMETERS, GET_CHANGER_PARAMETERS, GET_CHANGER_PARAMETERS structure [Storage Devices], PGET_CHANGER_PARAMETERS, PGET_CHANGER_PARAMETERS structure pointer [Storage Devices], _GET_CHANGER_PARAMETERS, ntddchgr/GET_CHANGER_PARAMETERS, ntddchgr/PGET_CHANGER_PARAMETERS, storage.get_changer_parameters, structs-changer_5c639124-5fc3-4fe8-8289-3bc8408723e0.xml"
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- ntddchgr.h
api_name:
- GET_CHANGER_PARAMETERS
product:
- Windows
targetos: Windows
req.typenames: GET_CHANGER_PARAMETERS, *PGET_CHANGER_PARAMETERS
---

# _GET_CHANGER_PARAMETERS structure


## -description


Retrieves the characteristics of the changer. 


## -struct-fields




### -field Size

The size of this structure in bytes. Set to <b>sizeof</b>(GET_CHANGER_PARAMETERS). In effect, this member indicates the version of this structure being used by the miniclass driver. 


### -field NumberTransportElements

Indicates the number of transport elements in the changer. For a SCSI changer, this is defined in the element address page. This value is almost always 1, because most changers have a single transport element, which can have one or two picker mechanisms. A changer that has two picker mechanisms on its transport must not be represented as having two transports, because pickers cannot be addressed individually. High-end media libraries can have dual and multiple transport elements for fault tolerance.


### -field NumberStorageElements

Indicates the number of storage elements (slots) in the changer. For a SCSI changer, this is defined in the element address page. This value represents the maximum number of slots available for this changer, including those in removable magazines, whether the magazines are installed. If <b>NumberCleanerSlots</b> is 1, then <b>NumberStorageElements</b> is 1 less than the maximum number of slots in the changer.


### -field NumberCleanerSlots

Indicates the number of storage elements (slots) for cleaner cartridges in the changer. For a SCSI changer, this value is not reported in mode sense data, so the miniclass driver must provide it. The miniclass driver should set <b>NumberCleanerSlots</b> to 1 only if the operator's guide for the changer identifies a specific slot as a cleaner slot. If <b>NumberCleanerSlots</b> is 1, then <b>FirstCleanerSlotAddress</b> indicates the zero-based address of the slot in which a drive cleaner should be inserted. If the changer does not support drive cleaning by programmatically moving the cleaner cartridge from its slot to a drive, the miniclass driver must set <b>NumberCleanerSlots</b> to 0. <b>NumberCleanerSlots</b> must not be greater than 1.


### -field NumberIEElements

Indicates the number of IEport elements the changer has for inserting and ejecting of media. For a SCSI changer, this is defined in the element address page. An IEport element must not be part of the storage element (slot) space, and it must be possible to transport media between the IEport and a slot using a MOVE MEDIUM SCSI command. If the changer has a door and not a true IEport, the miniclass driver must set <b>NumberIEElements</b> to 0.


### -field NumberDataTransferElements

Indicates the number of data transfer elements (drives) in the changer. For a SCSI changer, this is defined in the element address page. Unlike <b>NumberStorageElements</b>, which indicates the total number of possible slots whether the slots are actually present, <b>NumberDataTransferElements</b> indicates the number of drives that are actually present in the changer.


### -field NumberOfDoors

Indicates the number of doors that the changer has. For a SCSI changer, this value is not reported in mode sense data, so the miniclass driver must provide it. A door provides access to all media in the changer at once, unlike an IEport which provides access to one or more, but not all, media. A changer's door can be a physical front door or a single magazine that contains all media. If a changer supports only an IEport for inserting and ejecting media, the <b>NumberOfDoors</b> must be 0.


### -field FirstSlotNumber

Indicates the number used by the changer vendor to identify the first storage element (slot) in the changer to the end user, either by marking a magazine or by defining a slot numbering scheme in the changer's operators guide. <b>FirstSlotNumber</b> is typically 0 or 1, but it can be the first address in a consecutive range of slot addresses defined by the vendor. 


### -field FirstDriveNumber

Indicates the number used by the changer vendor to identify the first data transfer element (drive) in the changer to the end user. <b>FirstDriveNumber</b> is typically 0 or 1, but it can be the first address in a consecutive range of drive addresses defined by the vendor. 


### -field FirstTransportNumber

Indicates the number used by the changer vendor to identify the first (and usually only) transport element in the changer to the end user. <b>FirstTransportNumber</b> is typically 0 or 1, but it can be the first address in a consecutive range of transport addresses defined by the vendor. 


### -field FirstIEPortNumber

Indicates the number used by the changer vendor to identify the first (and usually only) IEport in the changer to the end user. <b>FirstIEPortNumber</b> is typically 0 or 1, but it can be the first address in a consecutive range of IEport addresses defined by the vendor. If <b>NumberIEElements</b> is 0, <b>FirstIEPortNumber</b> must also be 0.


### -field FirstCleanerSlotAddress

Indicates the number used by the changer vendor to identify the first (and only) slot address assigned to a drive cleaner cartridge to the end user. This must be the value defined by the vendor in the changer's operators guide. For example, if a changer has 8 slots numbered 1 through 8 and its operator's guide designates slot 8 as the drive cleaner slot, <b>FirstSlotNumber</b> would be 1 and <b>FirstCleanerSlotAddress</b> would be 8. If the same 8 slots were numbered 0 through 7, <b>FirstSlotNumber</b> would be 0 and <b>FirstCleanerSlotAddress</b> would be 7. If <b>NumberCleanerSlots</b> is 0, <b>FirstCleanerSlotAddress</b> must be 0.


### -field MagazineSize

Indicates the number of slots in the removable magazines in the changer. This member is valid only if CHANGER_CARTRIDGE_MAGAZINE is set in <b>Features0</b>.


### -field DriveCleanTimeout

Indicates twice the maximum number of seconds a cleaning is expected to take. The changer's drives should be cleaned by its cleaner cartridge in half the time specified by <b>DriveCleanTimeout</b>. For example, if a drive is typically cleaned in 300 seconds (5 minutes), <b>DriveCleanTimeout</b> should be set to 600.


### -field Features0

Indicates the features supported by the changer. This member can have one or more of the following values bitwise ORed together.





#### CHANGER_BAR_CODE_SCANNER_INSTALLED

The changer supports a bar code reader and the reader is installed. A miniclass driver must not hardcode this flag unless the changer's bar code reader is always installed. If the bar code reader is optional, the miniclass driver must determine whether the reader is actually installed and set the flag accordingly.





#### CHANGER_INIT_ELEM_STAT_WITH_RANGE

The changer can initialize elements within a specified range. For a SCSI changer, this flag indicates whether the changer supports the INITIALIZE ELEMENT STATUS WITH RANGE SCSI command.





#### CHANGER_CLOSE_IEPORT

The changer has an IEport and can retract the IEport programmatically.





#### CHANGER_OPEN_IEPORT

The changer has an IEport and can extend the IEport programmatically. 





#### CHANGER_STATUS_NON_VOLATILE

The changer uses nonvolatile memory for element status information.





#### CHANGER_EXCHANGE_MEDIA

Supports EXCHANGE MEDIUM SCSI command either by handling two volumes at a time or by using other changer elements to emulate this capability.





#### CHANGER_CLEANER_SLOT

Indicates that the changer has a specific slot designated for a cleaner cartridge. If this flag is set, <b>NumberCleanerSlots</b> must be one and <b>FirstCleanerSlotAddress</b> must specify the address of the cleaner slot. This bit can only be set if CHANGER_DRIVE_CLEANING_REQUIRED is set and CHANGER_CLEANER_OPS_NOT_SUPPORTED is reset. 





#### CHANGER_LOCK_UNLOCK

The changer's door, IEport, or keypad can be locked or unlocked programmatically. If this flag is set, <b>LockUnlockCapabilities</b> indicates which elements can be locked or unlocked.





#### CHANGER_CARTRIDGE_MAGAZINE

The changer uses removable cartridge magazines for some or all storage slots.





#### CHANGER_MEDIUM_FLIP

The changer's transport element supports flipping (rotating) media. For a SCSI changer, this flag reflects the rotate bit in the transport geometry parameters page. 





#### CHANGER_POSITION_TO_ELEMENT

The changer can position the transport to a particular destination. For a SCSI changer, this flag indicates whether the changer supports the POSITION TO ELEMENT SCSI command. If this flag is set, <b>PositionCapabilities</b> indicates the elements to which the transport can be positioned.





#### CHANGER_REPORT_IEPORT_STATE

The changer can report whether media is present in the IEport. Such a changer must have a sensor in the IEport to detect the presence or absence of media. 





#### CHANGER_STORAGE_DRIVE

The changer can use a drive as an independent storage element; that is, it can store media in the drive without reading it. For a SCSI changer, this flag reflects the state of the DT bit in the device capabilities page. 





#### CHANGER_STORAGE_IEPORT

The changer can use an IEport as an independent storage element. For a SCSI changer, this flag reflects the state of the I/E bit in the device capabilities page. 





#### CHANGER_STORAGE_SLOT

The changer can use a slot as an independent storage element for media. For a SCSI changer, this flag reflects the state of the ST bit in the device capabilities page. Slots are the normal storage location for media, so the changer must support this functionality.





#### CHANGER_STORAGE_TRANSPORT

The changer can use a transport as an independent storage element. For a SCSI changer, this flag reflects the state of the MT bit in the device capabilities page. 





#### CHANGER_DRIVE_CLEANING_REQUIRED

Indicates that the changer's drives might periodically report sense codes that indicate that the drive requires cleaning.





#### CHANGER_PREDISMOUNT_EJECT_REQUIRED

The changer requires an explicit command issued through a mass storage driver (tape, disk, or CD-ROM, for example) to eject media from a drive before the changer can move the media from a drive to a slot. If the changer ejects media automatically, the miniclass driver should clear this flag.





#### CHANGER_CLEANER_ACCESS_NOT_VALID

The ELEMENT_STATUS_ACCESS flag in a CHANGER_ELEMENT_STATUS structure for a data transport element is invalid when the transport element contains a cleaning cartridge.





#### CHANGER_DRIVE_EMPTY_ON_DOOR_ACCESS

The changer requires all drives to be empty (dismounted) before they can be accessed through its door. The miniclass driver should set this flag if the changer has static-sensitive drives that could be affected by an operator gaining access to the inside of the changer, or if the changer automatically ejects media from its drives when the operator attempts to physically open the door. 





#### CHANGER_VOLUME_IDENTIFICATION

The changer supports volume identification. For a SCSI changer, this flag indicates whether the changer supports the SEND VOLUME TAG and REQUEST VOLUME ELEMENT ADDRESS SCSI commands. 





#### CHANGER_VOLUME_SEARCH

The changer can search for volume information. For a SCSI changer, this flag indicates whether the changer supports the supports the SEND VOLUME TAG SCSI SCSI command with a send action code of TRANSLATE. 





#### CHANGER_VOLUME_ASSERT

The changer can verify volume information. For a SCSI changer, this flag indicates whether the changer supports the SEND VOLUME TAG SCSI command with a send action code of ASSERT.





#### CHANGER_VOLUME_REPLACE

The changer can replace volume information. For a SCSI changer, this flag indicates whether the changer supports the SEND VOLUME TAG SCSI command with a send action code of REPLACE. 





#### CHANGER_VOLUME_UNDEFINE

The changer can clear existing volume information. For a SCSI changer, this flag indicates whether the changer supports the supports the SEND VOLUME TAG SCSI command with a send action code of UNDEFINE. 





#### CHANGER_SERIAL_NUMBER_VALID

The serial number reported by GetProductData is valid and unique for all changers of this type. Serial numbers are not guaranteed to be unique across vendor and product lines. If the changer's serial number is unique according to this definition, the miniclass driver should set this flag and set SerialNumber in CHANGER_PRODUCT_DATA to the serial number.





#### CHANGER_PREMOUNT_EJECT_REQUIRED

The changer requires an explicit command issued through a mass storage driver to eject a drive mechanism before the changer can move media from a slot to the drive. For example, a changer with CD-ROM drives might require the tray to be presented to the robotic transport so a piece of media could be loaded onto the tray during a mount operation. If the changer ejects the mechanism automatically, the miniclass driver should clear this flag.





#### CHANGER_DEVICE_REINITIALIZE_CAPABLE

The changer can recalibrate its transport element in response to an explicit command. The changer class driver calls <b>ChangerReinitializeUnit</b> to initiate recalibration.





#### CHANGER_KEYPAD_ENABLE_DISABLE

The changer keypad can be enabled and disabled programmatically. 





#### CHANGER_RESERVED_BIT

Reserved to indicate <b>Features1</b> flags.


### -field Features1

Indicates additional features supported by the changer. This member can have one or more of the following values bitwise ORed together.





#### CHANGER_PREDISMOUNT_ALIGN_TO_SLOT

Indicates that the transport must be moved to the destination slot before moving the media from a drive to the slot. The bit CHANGER_PREDISMOUNT_ALIGN_TO_DRIVE must be reset if this is set.





#### CHANGER_PREDISMOUNT_ALIGN_TO_DRIVE

Indicates that the transport must be moved to the drive before moving media from the drive to a slot. The bit CHANGER_PREDISMOUNT_ALIGN_TO_SLOT must be reset if this is set.





#### CHANGER_CLEANER_AUTODISMOUNT

Indicates that the changer will move the cleaning cartridge back to its original slot automatically, after cleaning is finished. This bit can only be set if CHANGER_DRIVE_CLEANING_REQUIRED is set and CHANGER_CLEANER_OPS_NOT_SUPPORTED is reset. 





#### CHANGER_TRUE_EXCHANGE_CAPABLE

Device can manipulate two volumes at a time without using additional changer elements. 





#### CHANGER_SLOTS_USE_TRAYS

The changer uses removable trays in its slots, which require the media to be placed in a tray and the tray moved to the desired position.





#### CHANGER_RTN_MEDIA_TO_ORIGINAL_ADDR

Indicates that when moving volume from drive to slot, volume must go back into the same slot from which it was previously moved to the drive. 





#### CHANGER_CLEANER_OPS_NOT_SUPPORTED

Indicates that the changer's transport cannot be programmatically commanded by software above the changer driver to move a cleaning cartridge to a dirty drive. This bit can be set only if the CHANGER_DRIVE_CLEANING_REQUIRED bit is set. If this bit is set then both CHANGER_CLEANER_AUTODISMOUNT and CHANGER_CLEANER_SLOT must be reset.





#### CHANGER_IEPORT_USER_CONTROL_OPEN

The changer requires the user to manually open a closed IEport.





#### CHANGER_IEPORT_USER_CONTROL_CLOSE

The changer requires the user to manually close an open IEport.





#### CHANGER_MOVE_EXTENDS_IEPORT

The changer will extend the tray automatically whenever a command is issued to move media to an IEport.





#### CHANGER_MOVE_RETRACTS_IEPORT

The changer will retract the tray automatically whenever a command is issued to move media from an IEport.


### -field MoveFromTransport

Indicates whether the changer supports moving a piece of media from a transport element to another transport element, a storage slot, an IEport, or a drive. For a SCSI changer, this is defined in the device capabilities page. The transport is not typically the source or destination for moving or exchanging media. 

Callers can use the following masks to determine whether the changer can move media to a given element.





#### CHANGER_TO_TRANSPORT

The changer can carry out the operation from the specified element to a transport.





#### CHANGER_TO_SLOT

The changer can carry out the operation from the specified element to a storage slot.





#### CHANGER_TO_IEPORT

The changer can carry out the operation from the specified element to an IEport.





#### CHANGER_TO_DRIVE

The changer can carry out the operation from the specified element to a drive.


### -field MoveFromSlot

Indicates whether the changer supports moving medium from a storage slot to a transport element, another storage slot, an IEport, or a drive. Callers can use the masks described under <b>MoveFromTransport</b> to determine whether the changer supports the move. 


### -field MoveFromIePort

Indicates whether the changer supports moving medium from an IEport to a transport element, a storage slot, another IEport, or a drive. For a SCSI changer, this is defined in the device capabilities page. Callers can use the masks described under <b>MoveFromTransport</b> to determine whether the changer supports the move


### -field MoveFromDrive

Indicates whether the changer supports moving medium from a drive to a transport element, a storage slot, an IEport, or another drive. Callers can use the masks described under <b>MoveFromTransport</b> to determine whether the changer supports the move. 


### -field ExchangeFromTransport

Indicates whether the changer supports exchanging medium between a transport element and another transport element, a storage slot, an IEport, or a drive. Callers can use the masks described under <b>MoveFromTransport</b> to determine whether the changer supports the exchange. 


### -field ExchangeFromSlot

Indicates whether the changer supports exchanging medium between a storage slot and a transport element, another storage slot, an IEport, or a drive. Callers can use the masks described under <b>MoveFromTransport</b> to determine whether the changer supports the exchange. 


### -field ExchangeFromIePort

Indicates whether the changer supports exchanging medium between an IEport and a transport element, a storage slot, another IEport, or a drive. Callers can use the masks described under <b>MoveFromTransport</b> to determine whether the changer supports the exchange. 


### -field ExchangeFromDrive

Indicates whether the changer supports exchanging medium between a drive and a transport element, a storage slot, an IEport, or another drive. Callers can use the masks described under <b>MoveFromTransport</b> to determine whether the changer supports the exchange. 


### -field LockUnlockCapabilities

Indicates which elements of a changer can be locked or unlocked programmatically. This member is valid only if CHANGER_LOCK_UNLOCK is set in <b>Features0</b>. 

Callers can use the following masks to determine whether the changer can lock or unlock a particular element.





#### LOCK_UNLOCK_IEPORT

The changer can lock or unlock its IEport(s).



#### LOCK_UNLOCK_DOOR

The changer can lock or unlock its door.



#### LOCK_UNLOCK_KEYPAD

The changer can lock or unlock its keypad.


### -field PositionCapabilities

Indicates the elements to which a changer can position its transport. Callers can use the masks described under <b>MoveFromTransport</b> to determine whether the changer supports positioning the transport to a particular element. This member is valid only if CHANGER_POSITION_TO_ELEMENT is set in <b>Features0</b>. 


### -field Reserved1

Reserved for future use.


### -field Reserved2

Reserved for future use.


## -remarks



<b>GET_CHANGER_PARAMETERS</b> contains the parameters of a changer. The changer miniclass driver allocates and fills in this structure when requested by the changer class driver.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff551425">ChangerGetParameters</a>
 

 

