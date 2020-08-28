---
UID: NF:ucxcontroller.UcxControllerSetIdStrings
title: UcxControllerSetIdStrings function (ucxcontroller.h)
description: Updates the identifier strings of a controller after the controller has been initialized.
old-location: buses\ucxcontrollersetidstrings.htm
tech.root: usbref
ms.assetid: FC0F6C02-C53A-4F7E-B718-70788FA807F3
ms.date: 05/07/2018
keywords: ["UcxControllerSetIdStrings function"]
ms.keywords: UcxControllerSetIdStrings, UcxControllerSetIdStrings function [Buses], buses.ucxcontrollersetidstrings, ucxcontroller/UcxControllerSetIdStrings
req.header: ucxcontroller.h
req.include-header: Ucxclass.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10, version 1709
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ucxstubs.lib
req.dll: 
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - UcxControllerSetIdStrings
 - ucxcontroller/UcxControllerSetIdStrings
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Ucxstubs.lib
 - Ucxstubs.dll
api_name:
 - UcxControllerSetIdStrings
---

# UcxControllerSetIdStrings function


## -description

Updates the identifier strings
    of a controller after the controller has been initialized.

## -parameters

### -param Controller

<p> A handle to the UCX controller that the client driver received in a previous call to  the <a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/mt188033(v=vs.85)"><b>UcxControllerCreate</b></a> method.</p>

### -param ManufacturerNameString 

[in]
A string that contains the name of controller manufacturer.

### -param ModelNameString 

[in]
A string that contains the name of device model.

### -param ModelNumberString 

[in]
A string that contains the revision number of the device model.

## -returns

The function returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method might return one an appropriate <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values">NTSTATUS</a> error code.

