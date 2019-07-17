---
UID: NF:winspool.EnumPrintProcessorDatatypesA
title: EnumPrintProcessorDatatypesA function (winspool.h)
description: A print processor's EnumPrintProcessorDatatypes function enumerates the data types that the print processor supports.
old-location: print\enumprintprocessordatatypes.htm
tech.root: print
ms.assetid: 018880d0-0b0b-4130-bd8f-93814e40fe1e
ms.date: 04/20/2018
ms.keywords: EnumPrintProcessorDatatypes, EnumPrintProcessorDatatypes function [Print Devices], EnumPrintProcessorDatatypesA, print.enumprintprocessordatatypes, spoolfnc_f0686e8e-e1bc-448a-8dd1-eeccfb66dd9e.xml, winspool/EnumPrintProcessorDatatypes
ms.topic: function
f1_keywords:
 - "winspool/EnumPrintProcessorDatatypes"
req.header: winspool.h
req.include-header: Winspool.h
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- winspool.h
api_name:
- EnumPrintProcessorDatatypes
product:
- Windows
targetos: Windows
req.typenames: 
---

# EnumPrintProcessorDatatypesA function


## -description


A print processor's <b>EnumPrintProcessorDatatypes</b> function enumerates the data types that the print processor supports.


## -parameters




### -param pName [in, optional]

Caller-supplied pointer to a string representing name of the server on which the print processor is installed. If <b>NULL</b>, the server is the local system.


### -param pPrintProcessorName [in]

Caller-supplied pointer to a string representing the print processor name.


### -param Level

Caller-supplied value indicating the type of the structures to be returned in the buffer pointed to by <i>pDatatypes</i>. This value must be 1, indicating that the structure is DATATYPES_INFO_1.


### -param pDatatypes [out, optional]

Caller-supplied pointer to a buffer to receive an array of DATATYPES_INFO_1 structures, followed by a set of character strings representing data type names. The DATATYPES_INFO_1 structure is described in the Microsoft Windows SDK documentation. The structure member <i>pName</i> must be of type LPWSTR.


### -param cbBuf

Caller-supplied value representing the size, in bytes, of the buffer pointed to by <i>pDatatypes</i>.


### -param pcbNeeded [out]

Caller-supplied pointer to a location to receive the minimum required size for the buffer pointed to by <i>pDatatypes</i>.


### -param pcReturned [out]

Caller-supplied pointer to a location to receive the number of DATATYPES_INFO_1 structures returned in the buffer pointed to by <i>pDatatypes</i>.


## -returns



If the operation succeeds, the function should return <b>TRUE</b>. If the operation fails, the function should call <b>SetLastError</b> to set an error code, and then return <b>FALSE</b>.




## -remarks



Print processors are required to export an <b>EnumPrintProcessorDatatypes</b> function. The local print provider calls the function during initialization. The function is also called when an application calls the spooler's version of the same function.

The function must return an array of DATATYPES_INFO_1 structures, with each structure pointing to a string that represents a data type. The actual strings must also be included in the buffer, after the structure array. See <a href="https://docs.microsoft.com/windows-hardware/drivers/print/sample-print-processor">Sample Print Processor</a> for an example.

The function should return the number of DATATYPES_INFO_1 structures returned (that is, the number of data types supported) in the location pointed to by <i>pcReturned</i>.

The function should return the minimum required buffer size in the location pointed to by <i>pcbNeeded</i>. If the supplied buffer is too small, the function should specify a value for <i>pcbNeeded</i>, set the error code to ERROR_INSUFFICIENT_BUFFER, and return <b>FALSE</b>.



