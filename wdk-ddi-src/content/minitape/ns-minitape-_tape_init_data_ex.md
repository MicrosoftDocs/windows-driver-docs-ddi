---
UID: NS:minitape._TAPE_INIT_DATA_EX
title: TAPE_INIT_DATA_EX (minitape.h)
description: TAPE_INIT_DATA_EX defines values and routines that are specific to a Windows 2000 tape miniclass driver. The tape miniclass DriverEntry routine passes this information to the tape class driver to complete miniclass driver initialization.
old-location: storage\tape_init_data_ex.htm
tech.root: storage
ms.date: 03/29/2018
keywords: ["TAPE_INIT_DATA_EX structure"]
ms.keywords: "*PTAPE_INIT_DATA_EX, PTAPE_INIT_DATA_EX, PTAPE_INIT_DATA_EX structure pointer [Storage Devices], TAPE_INIT_DATA_EX, TAPE_INIT_DATA_EX structure [Storage Devices], _TAPE_INIT_DATA_EX, minitape/PTAPE_INIT_DATA_EX, minitape/TAPE_INIT_DATA_EX, storage.tape_init_data_ex, structs-tape_69291d6d-0f9e-4b6b-bb66-c40757bb5c69.xml"
req.header: minitape.h
req.include-header: Minitape.h
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
req.typenames: TAPE_INIT_DATA_EX, *PTAPE_INIT_DATA_EX
f1_keywords:
 - _TAPE_INIT_DATA_EX
 - minitape/_TAPE_INIT_DATA_EX
 - PTAPE_INIT_DATA_EX
 - minitape/PTAPE_INIT_DATA_EX
 - TAPE_INIT_DATA_EX
 - minitape/TAPE_INIT_DATA_EX
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - minitape.h
api_name:
 - _TAPE_INIT_DATA_EX
 - PTAPE_INIT_DATA_EX
 - TAPE_INIT_DATA_EX
---

# TAPE_INIT_DATA_EX structure

## -description

TAPE_INIT_DATA_EX defines values and routines that are specific to a Windows 2000 tape miniclass driver. The tape miniclass **DriverEntry** routine passes this information to the tape class driver to complete miniclass driver initialization.

## -struct-fields

### -field InitDataSize

Size of this structure, in bytes.

### -field VerifyInquiry

Specifies the entry point of the tape miniclass driver's [**TapeMiniVerifyInquiry**](nc-minitape-tape_verify_inquiry_routine.md) routine, which determines whether the driver supports a given device. This routine is required.

### -field QueryModeCapabilitiesPage

Directs the tape class driver when **TRUE** to pass a mode capabilities page to the tape miniclass driver's [**TapeMiniVerifyInquiry**](nc-minitape-tape_verify_inquiry_routine.md) and [**TapeMiniExtensionInit**](nc-minitape-tape_extension_init_routine.md) routines.

### -field MinitapeExtensionSize

Specifies the size, in bytes, of a driver-specific context area. If this member is nonzero, **ExtensionInit** must not be **NULL**. This value is optional and must be set to zero if not used.

### -field ExtensionInit

Pointer to the tape miniclass driver's [**TapeMiniExtensionInit**](nc-minitape-tape_extension_init_routine.md) routine, which initializes an optional minitape extension, if any. If **MiniTapeExtensionSize** is zero, **ExtensionInit** must be **NULL**.

### -field DefaultTimeOutValue

Specifies the number of seconds that the tape class driver waits for an SRB request before canceling it. If this value is zero, the tape class driver sets an appropriate default value. The tape class driver always uses the default time-out value for read and write requests. The routines contained in the TAPE_INIT_DATA_EX structure can override the default time-out value for device control requests by setting **TimeOutValue** in an SRB.

### -field TapeError

Pointer to the tape miniclass driver's [**TapeMiniTapeError**](nc-minitape-tape_error_routine.md) routine, which augments the error-handling activities of the tape class driver. This routine is optional. If one is not used, **TapeError** must be set to **NULL**.

### -field CommandExtensionSize

Specifies the size, in bytes, of a command extension to be allocated before the start of each tape command. A tape miniclass driver uses the command extension to store context during the processing of tape commands. Its size and internal structure are defined by the tape miniclass driver. A command extension is optional. If one is not used, **CommandExtensionSize** must be set to zero.

### -field CreatePartition

Pointer to the tape miniclass driver's [**TapeMiniCreatePartition**](nc-minitape-tape_process_command_routine.md) routine, which creates a partition on a tape. This routine is required.

### -field Erase

Pointer to the tape miniclass driver's [**TapeMiniErase**](nc-minitape-tape_process_command_routine.md) routine, which erases a tape. This routine is required.

### -field GetDriveParameters

Pointer to the tape miniclass driver's [**TapeMiniGetDriveParameters**](nc-minitape-tape_process_command_routine.md) routine, which handles requests to get drive parameters. This routine is required.

### -field GetMediaParameters

Pointer to the tape miniclass driver's [**TapeMiniGetMediaParameters**](nc-minitape-tape_process_command_routine.md) routine, which handles requests to get media parameters. This routine is required.

### -field GetPosition

Pointer to the tape miniclass driver's [**TapeMiniGetPosition**](nc-minitape-tape_process_command_routine.md) routine, which handles requests to get the position of a tape. This routine is required.

### -field GetStatus

Pointer to the tape miniclass driver's [**TapeMiniGetStatus**](nc-minitape-tape_process_command_routine.md) routine, which handles requests for status. This routine is required.

### -field Prepare

Pointer to the tape miniclass driver's [**TapeMiniPrepare**](nc-minitape-tape_process_command_routine.md) routine, which prepares a tape device. This routine is required.

### -field SetDriveParameters

Pointer to the tape miniclass driver's [**TapeMiniSetDriveParameters**](nc-minitape-tape_process_command_routine.md) routine, which sets drive parameters. This routine is required.

### -field SetMediaParameters

Pointer to the tape miniclass driver's [**TapeMiniSetMediaParameters**](nc-minitape-tape_process_command_routine.md) routine, which sets media parameters. This routine is required.

### -field SetPosition

Pointer to the tape miniclass driver's [**TapeMiniSetPosition**](nc-minitape-tape_process_command_routine.md) routine, which positions a tape. This routine is required.

### -field WriteMarks

Pointer to the tape miniclass driver's [**TapeMiniWriteMarks**](nc-minitape-tape_process_command_routine.md) routine, which writes marks to tape. This routine is required.

### -field PreProcessReadWrite

Pointer to the tape miniclass driver's [**TapeMiniPreProcessReadWrite**](nc-minitape-tape_process_command_routine.md) routine, which executes device-specific operations before all reads and writes. This routine is optional and is not needed by most drivers. If one is not used, **PreProcessReadWrite** must be **NULL**.

### -field TapeGetMediaTypes

Pointer to the tape miniclass driver's [**TapeMiniGetMediaTypes**](nc-minitape-tape_process_command_routine.md) routine, which gets a description of each media type supported by a tape device. This routine is required.

### -field MediaTypesSupported

Indicates the number of media types supported by the device.

### -field TapeWMIOperations

Pointer to the [**TapeMiniWMIControl**](nc-minitape-tape_process_command_routine.md) routine.

### -field Reserved

Reserved.

## -remarks

A tape miniclass driver's **DriverEntry** routine calls [**TapeClassZeroMemory**](nf-minitape-tapeclasszeromemory.md) to clear TAPE_INIT_DATA_EX, fills in the required members and any appropriate optional members, and [**TapeClassInitialize**](nf-minitape-tapeclassinitialize.md) with a pointer to this structure.

The names of the tape miniclass driver routines indicated in the member descriptions of this structure are just placeholder names. The prototype for these routines is declared in *newtape.h* as [**TAPE_PROCESS_COMMAND_ROUTINE**](nc-minitape-tape_process_command_routine.md).

The meaning of this prototype's parameters are different for each miniclass driver routine. For detailed information about how these parameters are used see the descriptions for each individual miniclass driver routine.

## -see-also

<a href="[**DriverEntry of Tape Miniclass Driver**](/windows-hardware/drivers/storage/driverentry-of-tape-miniclass-driver)

[**TapeClassInitialize**](nf-minitape-tapeclassinitialize.md)

[**TapeClassZeroMemory**](nf-minitape-tapeclasszeromemory.md)

[**TapeMiniCreatePartition**](nc-minitape-tape_process_command_routine.md)

[**TapeMiniErase**](nc-minitape-tape_process_command_routine.md)

[**TapeMiniExtensionInit**](nc-minitape-tape_extension_init_routine.md)

[**TapeMiniGetDriveParameters**](nc-minitape-tape_process_command_routine.md)

[**TapeMiniGetMediaParameters**](nc-minitape-tape_process_command_routine.md)

[**TapeMiniGetMediaTypes**](nc-minitape-tape_process_command_routine.md)

[**TapeMiniGetPosition**](nc-minitape-tape_process_command_routine.md)

[**TapeMiniGetStatus**](nc-minitape-tape_process_command_routine.md)

[**TapeMiniPrepare**](nc-minitape-tape_process_command_routine.md)

[**TapeMiniSetDriveParameters**](nc-minitape-tape_process_command_routine.md)

[**TapeMiniSetMediaParameters**](nc-minitape-tape_process_command_routine.md)

[**TapeMiniSetPosition**](nc-minitape-tape_process_command_routine.md)

[**TapeMiniTapeError**](nc-minitape-tape_error_routine.md)

[**TapeMiniVerifyInquiry**](nc-minitape-tape_verify_inquiry_routine.md)

[**TapeMiniWriteMarks**](nc-minitape-tape_process_command_routine.md)
