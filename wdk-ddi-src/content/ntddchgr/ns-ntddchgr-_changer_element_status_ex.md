---
UID: NS:ntddchgr._CHANGER_ELEMENT_STATUS_EX
title: _CHANGER_ELEMENT_STATUS_EX (ntddchgr.h)
description: The ChangerGetElementStatus routine returns status information in this structure.
old-location: storage\changer_element_status_ex.htm
tech.root: storage
ms.assetid: 1fb0d0f9-711a-4bd4-baf6-38ccbeae6e4a
ms.date: 03/29/2018
ms.keywords: "*PCHANGER_ELEMENT_STATUS_EX, CHANGER_ELEMENT_STATUS_EX, CHANGER_ELEMENT_STATUS_EX structure [Storage Devices], ELEMENT_STATUS_ACCESS, ELEMENT_STATUS_AVOLTAG, ELEMENT_STATUS_EXCEPT, ELEMENT_STATUS_EXENAB, ELEMENT_STATUS_FULL, ELEMENT_STATUS_ID_VALID, ELEMENT_STATUS_IMPEXP, ELEMENT_STATUS_INENAB, ELEMENT_STATUS_INVERT, ELEMENT_STATUS_LUN_VALID, ELEMENT_STATUS_NOT_BUS, ELEMENT_STATUS_PRODUCT_DATA, ELEMENT_STATUS_PVOLTAG, ELEMENT_STATUS_SVALID, ERROR_DRIVE_NOT_INSTALLED, ERROR_LABEL_QUESTIONABLE, ERROR_LABEL_UNREADABLE, ERROR_SLOT_NOT_PRESENT, ERROR_TRAY_MALFUNCTION, ERROR_UNHANDLED_ERROR, PCHANGER_ELEMENT_STATUS_EX, PCHANGER_ELEMENT_STATUS_EX structure pointer [Storage Devices], _CHANGER_ELEMENT_STATUS_EX, ntddchgr/CHANGER_ELEMENT_STATUS_EX, ntddchgr/PCHANGER_ELEMENT_STATUS_EX, storage.changer_element_status_ex, structs-changer_f620141a-83de-49c3-a79a-4f297e06955b.xml"
ms.topic: struct
f1_keywords:
 - "ntddchgr/CHANGER_ELEMENT_STATUS_EX"
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
- CHANGER_ELEMENT_STATUS_EX
product:
- Windows
targetos: Windows
req.typenames: CHANGER_ELEMENT_STATUS_EX, *PCHANGER_ELEMENT_STATUS_EX
---

# _CHANGER_ELEMENT_STATUS_EX structure


## -description


The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/mcd/nf-mcd-changergetelementstatus">ChangerGetElementStatus</a> routine returns status information in this structure. 


## -struct-fields




### -field Element

Specifies the element of type <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddchgr/ns-ntddchgr-_changer_element">CHANGER_ELEMENT</a>  to which this structure refers.


### -field SrcElementAddress

Specifies the element of type <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddchgr/ns-ntddchgr-_changer_element">CHANGER_ELEMENT</a> from which the media currently in this element was most recently moved. This member is valid only if ELEMENT_STATUS_SVALID is also set in <b>Flags</b>. This value must be a zero-based offset from the device-unique value.


### -field Flags

Indicates the status of the element, which can be one or more of the following values.



#### ELEMENT_STATUS_FULL

The element contains a piece of media. This flag is valid if <b>ElementType</b> in the <b>Element</b> member is <b>ChangerDrive</b>, <b>ChangerSlot</b>, or <b>ChangerTransport</b>. If <b>ElementType</b> is <b>ChangerIEPort</b>, this flag is valid only if CHANGER_REPORT_IEPORT_STATE is also set in <b>Features0</b> of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddchgr/ns-ntddchgr-_get_changer_parameters">GET_CHANGER_PARAMETERS</a>.



#### ELEMENT_STATUS_IMPEXP

The media in this element was placed there by an operator. This flag is valid only if <b>ElementType</b> in the <b>Element</b> member is <b>ChangerIEPort</b>. 



#### ELEMENT_STATUS_EXCEPT

The element is in an abnormal state. Check the <b>ExceptionCode</b> member for more information.



#### ELEMENT_STATUS_ACCESS

The changer's transport element can access the piece of media in this element. The miniclass driver clears this flag to indicate that the media is not accessible for one of the following reasons: If <b>ElementType</b> in the <b>Element</b> member is <b>ChangerSlot</b>, the slot is not present in the changer (for example, the magazine containing the slot has been physically removed). If <b>ElementType</b> is <b>ChangerDrive</b>, the drive is broken or has been removed. If <b>ElementType</b> is <b>ChangerIEPort</b>, the IEport is extended.



#### ELEMENT_STATUS_EXENAB

The element supports export of media through the changer's IEport.



#### ELEMENT_STATUS_INENAB

The element supports import of media through the changer's IEport.



#### ELEMENT_STATUS_LUN_VALID

The device number in the <b>Lun</b> member is valid. This flag is valid only if <b>ElementType</b> in the <b>Element</b> member is <b>ChangerDrive</b>. 



#### ELEMENT_STATUS_ID_VALID

The SCSI target ID in the <b>TargetID</b> member is valid. This flag is valid only if <b>ElementType</b> in the <b>Element</b> member is <b>ChangerDrive</b>. 



#### ELEMENT_STATUS_NOT_BUS

The drive at the address indicated by <b>Lun</b> and <b>TargetID</b> is on a different SCSI bus than the changer itself. 



#### ELEMENT_STATUS_PRODUCT_DATA

The serial number in the <b>SerialNumber</b> member is valid.



#### ELEMENT_STATUS_INVERT

The media in the element was flipped. This flag is valid only if the ELEMENT_STATUS_SVALID flag is also set.



#### ELEMENT_STATUS_SVALID

The <b>SourceElement</b> member and ELEMENT_STATUS_INVERT flag are both valid.



#### ELEMENT_STATUS_PVOLTAG

Primary volume information in the <b>PrimaryVolumeID</b> member is valid.



#### ELEMENT_STATUS_AVOLTAG

Alternate volume information in the <b>AlternateVolumeID</b> member is valid.


### -field ExceptionCode

Indicates that the element is in an abnormal state. This member is valid only if ELEMENT_STATUS_EXCEPT is set in <b>Flags</b>. <b>ExceptionCode</b> can be set to one of the following values. 



#### ERROR_LABEL_UNREADABLE

The changer's bar code reader could not read the bar code label on the piece of media in this element, because the media is missing, damaged, improperly positioned, or upside down.



#### ERROR_LABEL_QUESTIONABLE

The label might be invalid due to a unit attention condition.



#### ERROR_SLOT_NOT_PRESENT

The slot at this element address is currently not installed in the changer. A miniclass driver sets this code for each slot in a removable magazine to indicate that the magazine has been removed.



#### ERROR_DRIVE_NOT_INSTALLED

The drive at this element address is absent. If a changer can continue to operate without the drive, its miniclass driver sets ERROR_DRIVE_NOT_INSTALLED for the drive. 



#### ERROR_TRAY_MALFUNCTION

The drive at this element address has a tray that must be extended to load or remove media, and the tray is not extending as required.



#### ERROR_UNHANDLED_ERROR

Unknown error condition.


### -field TargetId

Specifies the SCSI target ID of the drive at this element address for a SCSI changer. This member is valid only if <b>ElementType</b> in the <b>Element</b> member is <b>ChangerDrive</b> and ELEMENT_STATUS_ID_VALID is set in <b>Flags</b>. 


### -field Lun

Specifies the SCSI device number of the drive at this element address. This member is valid only if <b>ElementType</b> in the <b>Element</b> member is <b>ChangerDrive</b> and ELEMENT_STATUS_LUN_VALID is set in <b>Flags</b>.


### -field Reserved

Reserved for future use. The value of this member must be zero.


### -field PrimaryVolumeID

Specifies the primary volume identifier for the media. If the changer supports a bar code reader and the reader is installed (as indicated by CHANGER_BAR_CODE_SCANNER_INSTALLED in <b>Features0</b> of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddchgr/ns-ntddchgr-_get_changer_parameters">GET_CHANGER_PARAMETERS</a>), the miniclass driver must set <b>PrimaryVolumeID</b> to the bar code of the media. If the changer does not support a bar code reader, the miniclass driver should set <b>PrimaryVolumeID</b> to the value previously assigned to the media using the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/mcd/nf-mcd-changerqueryvolumetags">ChangerQueryVolumeTags</a> routine with an ASSERT_PRIMARY or REPLACE_PRIMARY action. This member is valid only if ELEMENT_STATUS_PVOLTAG is also set in <b>Flags</b>. If the volume identifier is missing or unreadable, the miniclass driver should clear this flag and set the appropriate error status. This identifier must be no larger than MAX_VOLUME_ID_SIZE bytes. 


### -field AlternateVolumeID

Specifies alternate volume identification for the media. This member is valid for two-sided media only, and pertains to the ID of the inverted side. It never represents a bar code. The miniclass driver must set <b>AlternateVolumeID</b> to the value previously assigned to the media using the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/mcd/nf-mcd-changerqueryvolumetags">ChangerQueryVolumeTags</a> routine with an ASSERT_ALTERNATE or REPLACE_ALTERNATE action. The identifier must be no larger than MAX_VOLUME_ID_SIZE bytes and is valid only if ELEMENT_STATUS_AVOLTAG is also set in <b>Flags</b>.


### -field VendorIdentification

Contains the vendor ID. This identifier must be no larger than VENDOR_ID_LENGTH bytes. 


### -field ProductIdentification

Contains the product ID. This identifier must be no larger than PRODUCT_ID_LENGTH bytes. 


### -field SerialNumber

Contains the serial number. This identifier must be no larger than SERIAL_NUMBER_LENGTH bytes. 


## -remarks



The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/mcd/nf-mcd-changergetelementstatus">ChangerGetElementStatus</a> routine returns status information in this structure if vendor, product, or serial number information is needed. Otherwise, <b>ChangerGetElementStatus</b> returns status information in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddchgr/ns-ntddchgr-_changer_element_status">CHANGER_ELEMENT_STATUS</a> structure.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddchgr/ns-ntddchgr-_changer_element">CHANGER_ELEMENT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddchgr/ns-ntddchgr-_changer_element_status">CHANGER_ELEMENT_STATUS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/mcd/nf-mcd-changergetelementstatus">ChangerGetElementStatus</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddchgr/ns-ntddchgr-_get_changer_parameters">GET_CHANGER_PARAMETERS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddchgr/ni-ntddchgr-ioctl_changer_get_element_status">IOCTL_CHANGER_GET_ELEMENT_STATUS</a>
 

 

