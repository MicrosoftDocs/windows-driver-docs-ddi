---
UID: NI:ntddchgr.IOCTL_CHANGER_INITIALIZE_ELEMENT_STATUS
title: IOCTL_CHANGER_INITIALIZE_ELEMENT_STATUS (ntddchgr.h)
description: Initializes the status of all elements or of specified number of elements of a particular type.
old-location: storage\ioctl_changer_initialize_element_status.htm
tech.root: storage
ms.assetid: 25cbb42a-7263-47b7-84c7-cfcb41a858c8
ms.date: 03/29/2018
ms.keywords: IOCTL_CHANGER_INITIALIZE_ELEMENT_STATUS, IOCTL_CHANGER_INITIALIZE_ELEMENT_STATUS control, IOCTL_CHANGER_INITIALIZE_ELEMENT_STATUS control code [Storage Devices], k307_c36a7809-093c-4172-8443-58d178e9dd87.xml, ntddchgr/IOCTL_CHANGER_INITIALIZE_ELEMENT_STATUS, storage.ioctl_changer_initialize_element_status
f1_keywords:
 - "ntddchgr/IOCTL_CHANGER_INITIALIZE_ELEMENT_STATUS"
req.header: ntddchgr.h
req.include-header: Ntddchgr.h
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
- Ntddchgr.h
api_name:
- IOCTL_CHANGER_INITIALIZE_ELEMENT_STATUS
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_CHANGER_INITIALIZE_ELEMENT_STATUS IOCTL


## -description



Initializes the status of all elements or of specified number of elements of a particular type. 




## -ioctlparameters




### -input-buffer


       The buffer at <b>Irp->AssociatedIrp.SystemBuffer</b> contains an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddchgr/ns-ntddchgr-_changer_initialize_element_status">CHANGER_INITIALIZE_ELEMENT_STATUS</a> structure that indicates the element type and the number of elements to initialize. If the <b>BarCodeScan</b> member is <b>TRUE</b> and CHANGER_BAR_CODE_SCANNER_INSTALLED is also set in <b>Features0</b> of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddchgr/ns-ntddchgr-_get_changer_parameters">GET_CHANGER_PARAMETERS</a>, the elements should be initialized using a bar code scan. 


### -input-buffer-length

<b>Parameters.DeviceIoControl.InputBufferLength</b> in the I/O stack location indicates the size, in bytes, of the parameter buffer, which must be >= <b>sizeof</b>(CHANGER_INITIALIZE_ELEMENT_STATUS). 


### -output-buffer

None.


### -output-buffer-length

None.


### -in-out-buffer








### -inout-buffer-length








### -status-block

The <b>Information</b> field is set to <b>sizeof</b>(CHANGER_INITIALIZE_ELEMENT_STATUS). The <b>Status</b> field is set to STATUS_SUCCESS, or possibly to STATUS_INFO_LENGTH_MISMATCH, STATUS_INSUFFICIENT_RESOURCES, STATUS_INVALID_ELEMENT_ADDRESS, or STATUS_INVALID_PARAMETER. 


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddchgr/ns-ntddchgr-_changer_initialize_element_status">CHANGER_INITIALIZE_ELEMENT_STATUS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/mcd/nf-mcd-changerinitializeelementstatus">ChangerInitializeElementStatus</a>
 

 

