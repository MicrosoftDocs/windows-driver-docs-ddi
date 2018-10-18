---
UID: NF:ucxcontroller.UcxControllerSetIdStrings
title: UcxControllerSetIdStrings function
author: windows-driver-content
description: Updates the identifier strings of a controller after the controller has been initialized.
old-location: buses\ucxcontrollersetidstrings.htm
tech.root: usbref
ms.assetid: FC0F6C02-C53A-4F7E-B718-70788FA807F3
ms.date: 5/7/2018
ms.keywords: UcxControllerSetIdStrings, UcxControllerSetIdStrings function [Buses], buses.ucxcontrollersetidstrings, ucxcontroller/UcxControllerSetIdStrings
ms.topic: function
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Ucxstubs.lib
-	Ucxstubs.dll
api_name:
-	UcxControllerSetIdStrings
product:
- Windows
targetos: Windows
req.typenames: 
---

# UcxControllerSetIdStrings function


## -description


Updates the identifier strings
    of a controller after the controller has been initialized.


## -parameters




### -param Controller

<p> A handle to the UCX controller that the client driver received in a previous call to  the <a href="https://msdn.microsoft.com/library/Mt188033(v=VS.85).aspx"><b>UcxControllerCreate</b></a> method.</p>


### -param ManufacturerNameString [in]

A string that contains the name of controller manufacturer.


### -param ModelNameString [in]

A string that contains the name of device model.


### -param ModelNumberString [in]

A string that contains the revision number of the device model.


## -returns



The function returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method might return one an appropriate <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NTSTATUS</a> error code. 



