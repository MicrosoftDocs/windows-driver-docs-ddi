---
UID: NS:ntddchgr._CHANGER_ELEMENT_STATUS
title: _CHANGER_ELEMENT_STATUS (ntddchgr.h)
description: The ChangerGetElementStatus routine returns status information in this structure.
old-location: storage\changer_element_status.htm
tech.root: storage
ms.date: 03/29/2018
keywords: ["CHANGER_ELEMENT_STATUS structure"]
ms.keywords: "*PCHANGER_ELEMENT_STATUS, CHANGER_ELEMENT_STATUS, CHANGER_ELEMENT_STATUS structure [Storage Devices], PCHANGER_ELEMENT_STATUS, PCHANGER_ELEMENT_STATUS structure pointer [Storage Devices], _CHANGER_ELEMENT_STATUS, ntddchgr/CHANGER_ELEMENT_STATUS, ntddchgr/PCHANGER_ELEMENT_STATUS, storage.changer_element_status, structs-changer_6dd054a8-1224-42f1-ab26-29b2c108ce27.xml"
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
targetos: Windows
req.typenames: CHANGER_ELEMENT_STATUS, *PCHANGER_ELEMENT_STATUS
f1_keywords:
 - _CHANGER_ELEMENT_STATUS
 - ntddchgr/_CHANGER_ELEMENT_STATUS
 - PCHANGER_ELEMENT_STATUS
 - ntddchgr/PCHANGER_ELEMENT_STATUS
 - CHANGER_ELEMENT_STATUS
 - ntddchgr/CHANGER_ELEMENT_STATUS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntddchgr.h
api_name:
 - _CHANGER_ELEMENT_STATUS
 - PCHANGER_ELEMENT_STATUS
 - CHANGER_ELEMENT_STATUS
---

# _CHANGER_ELEMENT_STATUS structure


## -description

The <a href="/windows-hardware/drivers/ddi/mcd/nf-mcd-changergetelementstatus">ChangerGetElementStatus</a> routine returns status information in this structure.

## -struct-fields

### -field Element

Specifies the element of type <a href="/windows-hardware/drivers/ddi/ntddchgr/ns-ntddchgr-_changer_element">CHANGER_ELEMENT</a>  to which this structure refers.

### -field SrcElementAddress

Specifies the element of type <a href="/windows-hardware/drivers/ddi/ntddchgr/ns-ntddchgr-_changer_element">CHANGER_ELEMENT</a> from which the media currently in this element was most recently moved. This member is valid only if ELEMENT_STATUS_SVALID is also set in <b>Flags</b>. This value must be a zero-based offset from the device-unique value.

### -field Flags

Indicates the status of the element, which can be one or more of the following values.





#### ELEMENT_STATUS_FULL

The element contains a piece of media. This flag is valid if <b>ElementType</b> in the <b>Element</b> member is <b>ChangerDrive</b>, <b>ChangerSlot</b>, or <b>ChangerTransport</b>. If <b>ElementType</b> is <b>ChangerIEPort</b>, this flag is valid only if CHANGER_REPORT_IEPORT_STATE is also set in <b>Features0</b> of GET_CHANGER_PARAMETERS.





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

Specifies the primary volume identifier for the media. If the changer supports a bar code reader and the reader is installed (as indicated by CHANGER_BAR_CODE_SCANNER_INSTALLED in <b>Features0</b> of GET_CHANGER_PARAMETERS), the miniclass driver must set <b>PrimaryVolumeID</b> to the bar code of the media. If the changer does not support a bar code reader, the miniclass driver should set <b>PrimaryVolumeID</b> to the value previously assigned to the media using the <b>ChangerQueryVolumeTags</b> routine with an ASSERT_PRIMARY or REPLACE_PRIMARY action. This member is valid only if ELEMENT_STATUS_PVOLTAG is also set in <b>Flags</b>. If the volume identifier is missing or unreadable, the miniclass driver should clear this flag and set the appropriate error status. This identifier must be no larger than MAX_VOLUME_ID_SIZE bytes.

### -field AlternateVolumeID

Specifies alternate volume identification for the media. This member is valid for two-sided media only, and pertains to the ID of the inverted side. It never represents a bar code. The miniclass driver must set <b>AlternateVolumeID</b> to the value previously assigned to the media using the <b>ChangerQueryVolumeTags</b> routine with an ASSERT_ALTERNATE or REPLACE_ALTERNATE action. The identifier must be no larger than MAX_VOLUME_ID_SIZE bytes and is valid only if ELEMENT_STATUS_AVOLTAG is also set in <b>Flags</b>.

## -remarks

For most element types, changer miniclass drivers use CHANGER_ELEMENT_STATUS to report the status of specified elements to the changer class driver. Some elements of type <b>ChangerDrive</b>, however, return product information data. If the device provides product information, the miniclass driver will report the element status data in a structure of type <a href="/windows-hardware/drivers/ddi/ntddchgr/ns-ntddchgr-_changer_element_status_ex">CHANGER_ELEMENT_STATUS_EX</a> instead of using CHANGER_ELEMENT_STATUS. The miniclass driver indicates that product information is present by setting ELEMENT_STATUS_PRODUCT_DATA in the <b>Flags</b> member of the structure.

## -see-also

<a href="/windows-hardware/drivers/ddi/ntddchgr/ns-ntddchgr-_changer_element">CHANGER_ELEMENT</a>



<a href="/windows-hardware/drivers/ddi/ntddchgr/ns-ntddchgr-_changer_element_status_ex">CHANGER_ELEMENT_STATUS_EX</a>



<a href="/windows-hardware/drivers/ddi/mcd/nf-mcd-changergetelementstatus">ChangerGetElementStatus</a>



<a href="/windows-hardware/drivers/ddi/mcd/nf-mcd-changerqueryvolumetags">ChangerQueryVolumeTags</a>



<a href="/windows-hardware/drivers/ddi/ntddchgr/ni-ntddchgr-ioctl_changer_get_element_status">IOCTL_CHANGER_GET_ELEMENT_STATUS</a>

