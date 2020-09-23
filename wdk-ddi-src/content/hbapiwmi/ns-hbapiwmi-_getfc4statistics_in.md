---
UID: NS:hbapiwmi._GetFC4Statistics_IN
title: _GetFC4Statistics_IN (hbapiwmi.h)
description: The GetFC4Statistics_IN structure is used to pass input parameter data to the GetFC4Statistics WMI method.
old-location: storage\getfc4statistics_in.htm
tech.root: storage
ms.assetid: 10e3c823-97e3-47e9-8545-94cd186e5b59
ms.date: 03/29/2018
keywords: ["GetFC4Statistics_IN structure"]
ms.keywords: "*PGetFC4Statistics_IN, GetFC4Statistics_IN, GetFC4Statistics_IN structure [Storage Devices], PGetFC4Statistics_IN, PGetFC4Statistics_IN structure pointer [Storage Devices], _GetFC4Statistics_IN, hbapiwmi/GetFC4Statistics_IN, hbapiwmi/PGetFC4Statistics_IN, storage.getfc4statistics_in, structs-Fibre_17ea3e0e-1cf9-4cf8-9128-1152e610847c.xml"
req.header: hbapiwmi.h
req.include-header: Hbapiwmi.h
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
req.typenames: GetFC4Statistics_IN, *PGetFC4Statistics_IN
f1_keywords:
 - _GetFC4Statistics_IN
 - hbapiwmi/_GetFC4Statistics_IN
 - PGetFC4Statistics_IN
 - hbapiwmi/PGetFC4Statistics_IN
 - GetFC4Statistics_IN
 - hbapiwmi/GetFC4Statistics_IN
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - hbapiwmi.h
api_name:
 - GetFC4Statistics_IN
---

# _GetFC4Statistics_IN structure


## -description

The GetFC4Statistics_IN structure is used to pass input parameter data to the <a href="/windows-hardware/drivers/storage/getfc4statistics">GetFC4Statistics</a> WMI method.

## -struct-fields

### -field PortWWN

Contains the worldwide name for the local port of type Nx_Port whose traffic statistics are to be reported.

### -field FC4Type

Contains a value that indicates the type FC-4 protocol. For an explanation of FC4 types, see the T11 committee's <i>Fibre Channel Generic Services - 4 </i>specification.

## -remarks

The method <a href="/windows-hardware/drivers/storage/getfc4statistics">GetFC4Statistics</a> queries an HBA and port of type Nx_Port for traffic statistics associated with the indicated FC-4 protocol.

The WMI tool suite generates a declaration of the GetFC4Statistics_IN structure in <i>Hbapiwmi.h </i>when it compiles the <a href="/windows-hardware/drivers/storage/msfc-hbaadaptermethods-wmi-class">MSFC_HBAAdapterMethods WMI Class</a>.

For a definition of Nx_Port, see the T11 committee's specification for <i>Fibre Channel HBA API</i> (FC-HBA).

## -see-also

<a href="/windows-hardware/drivers/storage/getfc4statistics">GetFC4Statistics</a>