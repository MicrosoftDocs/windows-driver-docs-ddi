---
UID: NF:winddiui.DrvConvertDevMode
title: DrvConvertDevMode function
author: windows-driver-content
description: A printer interface DLL's DrvConvertDevMode function converts a printer's DEVMODEW structure from one version to another.
old-location: print\drvconvertdevmode.htm
old-project: print
ms.assetid: eb0402a8-22ce-417f-9b19-25b357451307
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: DrvConvertDevMode, DrvConvertDevMode function [Print Devices], print.drvconvertdevmode, print_interface-graphics_ceabaf66-f730-4243-85a7-ffcee065192b.xml, winddiui/DrvConvertDevMode
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: winddiui.h
req.include-header: Winddiui.h
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	winddiui.h
apiname:
-	DrvConvertDevMode
product: Windows
targetos: Windows
req.typenames: WINBIO_VERSION, *PWINBIO_VERSION
req.product: Windows 10 or later.
---

# DrvConvertDevMode function


## -description


A printer interface DLL's <b>DrvConvertDevMode</b> function converts a printer's <a href="https://msdn.microsoft.com/library/windows/hardware/ff552837">DEVMODEW</a> structure from one version to another.


## -syntax


````
BOOL DrvConvertDevMode(
  _In_    LPTSTR   pPrinterName,
  _In_    PDEVMODE pdmIn,
  _Out_   PDEVMODE pdmOut,
  _Inout_ PLONG    pcbNeeded,
  _In_    DWORD    fMode
);
````


## -parameters




### -param pPrinterName [in]

Caller-supplied pointer to a printer name string. For more information about this parameter, see the following Remarks section.


### -param pdmIn [in]

Caller-supplied pointer to an input DEVMODEW structure. If <i>fMode</i> is CDM_DRIVER_DEFAULT, this pointer is <b>NULL</b>.


### -param pdmOut [out]

Caller-supplied pointer to a buffer to receive an output DEVMODEW structure. If <i>fMode</i> is CDM_CONVERT the buffer contains, on input, a valid DEVMODEW structure indicating the target driver version.


### -param pcbNeeded [in, out]

Caller-supplied pointer to the size, in bytes, of the buffer pointed to by <i>pdmOut</i>. On output, the printer interface DLL should overwrite the received size value with the actual size of the converted DEVMODEW structure. If the received buffer is too small, the printer interface DLL should overwrite the received size value with the required buffer size.


### -param fMode [in]

Caller-supplied bit flag indicating the type of operation to be performed. This can be one of the following flags:





#### CDM_CONVERT

The function should convert the contents of the input DEVMODEW structure (pointed to by <i>pdmIn</i>) into a new DEVMODEW structure, and place the result in the DEVMODEW structure pointed to by <i>pdmOut</i>. The initial contents of the received output DEVMODEW structure (pointed to by <i>pdmOut</i>) should be used to determine the output version.





#### CDM_CONVERT351

The function should convert the contents of the input DEVMODEW structure (pointed to by <i>pdmIn</i>), creating an output DEVMODEW structure that is compatible with Windows NT 3.51, and place the result in the DEVMODEW structure pointed to by <i>pdmOut</i>.

If the driver does not support a DEVMODEW structure for Windows NT 3.51, the function should convert the input DEVMODEW to the current version.





#### CDM_DRIVER_DEFAULT

The function should copy the current version of its default DEVMODEW structure to the buffer pointed to by <i>pdmOut</i>.


## -returns



If the operation succeeds, the function should return <b>TRUE</b>; otherwise, it should call SetLastError to set an error code, and return <b>FALSE</b>.




## -remarks



In a client/server environment, a client might be running one version of the operating system or printer driver while the server (spooler) is running another, which means a printer's DEVMODEW structure definition might be inconsistent between the client and server. The <b>DrvConvertDevMode</b> function must be capable of performing conversions from one version of the printer's DEVMODEW structure to another.

When converting from one DEVMODEW version to another, both public and private DEVMODEW members must be included.

The printer name pointed to by <i>pPrinterName</i> can be used as an input argument to the <b>OpenPrinter</b> function (described in the Microsoft Windows SDK documentation), which can be called to obtain stored default values when the CDM_DRIVER_DEFAULT flag is received. Note that the printer name string must be not be modified in any way prior to a call to <b>OpenPrinter</b>. In addition, a call to <b>OpenPrinter</b> must be in the same thread as was used to call <b>DrvConvertDevMode</b>. 

The function should verify that both <i>pdmIn</i> and <i>pdmOut</i> (if applicable) point to valid DEVMODEW structures. If they do not, the function should call SetLastError(ERROR_INVALID_PARAMETER) and return <b>FALSE</b>. If the output DEVMODEW size specified by <i>pcbNeeded</i> is too small, the driver should overwrite the size value supplied by <i>pcbNeeded</i> with the required buffer size, call SetLastError(ERROR_INSUFFICIENT_BUFFER), and return <b>FALSE</b>.

The <b>DrvConvertDevMode</b> function runs in the spooler's context and must therefore not display a user interface.

When <b>DrvConvertDevMode</b> is called with a <b>NULL</b> DEVMODEW structure pointer in the <i>pdmOut </i>parameter to get the buffer size, the driver is expected to set the last error to ERROR_INSUFFICIENT_BUFFER. If the last error is not set to this value, the spooler assumes a general error.



