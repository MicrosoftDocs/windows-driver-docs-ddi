---
UID: NC:usbcamdi.PFNUSBCAMD_BulkReadWrite
title: PFNUSBCAMD_BulkReadWrite (usbcamdi.h)
description: The USBCAMD_BulkReadWrite service performs a read or write operation on the specified bulk pipe.
tech.root: stream
ms.date: 03/08/2023
keywords: ["PFNUSBCAMD_BulkReadWrite callback function"]
ms.keywords: PFNUSBCAMD_BulkReadWrite, USBCAMD_BulkReadWrite, USBCAMD_BulkReadWrite routine [Streaming Media Devices], stream.usbcamd_bulkreadwrite, usbcamdi/USBCAMD_BulkReadWrite, usbcmdpr_6044cfed-1a8c-48a5-ac28-16c8ac151fcc.xml
req.header: usbcamdi.h
req.include-header: Usbcamdi.h
req.target-type: Desktop
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
req.typenames: 
f1_keywords:
 - PFNUSBCAMD_BulkReadWrite
 - usbcamdi/PFNUSBCAMD_BulkReadWrite
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - usbcamdi.h
api_name:
 - PFNUSBCAMD_BulkReadWrite
---

# PFNUSBCAMD_BulkReadWrite callback function

## -description

The **USBCAMD_BulkReadWrite** service performs a read or write operation on the specified bulk pipe.

## -parameters

### -param DeviceContext [in]

Pointer to the camera minidriver's device context.

### -param PipeIndex [in]

Specifies the index of the bulk pipe.

### -param Buffer [in]

Pointer to the read or write buffer. If this parameter is set to **NULL** for a read request, USBCAMD pulls a data SRB from the SRB read queue of the stream associated with this pipe. Write requests with a **NULL** buffer pointer are only permitted on the still pin if an SRB_WRITE_DATA request has been submitted to the still pin.

### -param BufferLength [in]

Specifies the length of the read/write buffer in bytes.

### -param CommandComplete [in]

Pointer to a camera minidriver defined [CommandCompleteFunction](./nc-usbcamdi-pcommand_complete_function.md), which is called when the bulk read or write is completed. This value can be **NULL**.

### -param CommandContext [in]

Pointer to a block of memory, that is passed as an argument to the camera minidriver defined [CommandCompleteFunction](./nc-usbcamdi-pcommand_complete_function.md).

## -returns

**USBCAMD_BulkReadWrite** returns STATUS_SUCCESS if the call was successful. Other possible error codes include:

| Return code | Description |
|---|---|
| **STATUS_FILE_CLOSED** | The device has been removed. |
| **STATUS_INVALID_PARAMETER** | USBCAMD may return STATUS_INVALID_PARAMETER for a number of reasons, including:<br><br>The value passed in the *PipeIndex* argument is invalid.<br><br>The type of the pipe specified by the *PipeIndex* argument represents an invalid type of pipe.<br><br>A bulk read/write request already exists. The *Buffer* argument is **NULL**. |
| **STATUS_INSUFFICIENT_RESOURCES** | There are insufficient resources to schedule a transfer. |

## -remarks

USBCAMD can accept one read and one write request at a time.

**USBCAMD_BulkReadWrite** is not available in USBCAMD version 1.0.

## -see-also

[CommandCompleteFunction](./nc-usbcamdi-pcommand_complete_function.md)

[**USBCAMD_INTERFACE**](./ns-usbcamdi-usbcamd_interface.md)