---
UID: NS:hbapiwmi._GetFcpTargetMapping_IN
title: _GetFcpTargetMapping_IN (hbapiwmi.h)
description: The GetFcpTargetMapping_IN structure is used to report the output parameter data of the GetFcpTargetMapping WMI method to the WMI client.
old-location: storage\getfcptargetmapping_in.htm
tech.root: storage
ms.date: 03/29/2018
keywords: ["GetFcpTargetMapping_IN structure"]
ms.keywords: "*PGetFcpTargetMapping_IN, GetFcpTargetMapping_IN, GetFcpTargetMapping_IN structure [Storage Devices], PGetFcpTargetMapping_IN, PGetFcpTargetMapping_IN structure pointer [Storage Devices], _GetFcpTargetMapping_IN, hbapiwmi/GetFcpTargetMapping_IN, hbapiwmi/PGetFcpTargetMapping_IN, storage.getfcptargetmapping_in, structs-Fibre_1c84c265-fc0a-4d56-bdb9-7a10ef80b707.xml"
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
req.typenames: GetFcpTargetMapping_IN, *PGetFcpTargetMapping_IN
f1_keywords:
 - _GetFcpTargetMapping_IN
 - hbapiwmi/_GetFcpTargetMapping_IN
 - PGetFcpTargetMapping_IN
 - hbapiwmi/PGetFcpTargetMapping_IN
 - GetFcpTargetMapping_IN
 - hbapiwmi/GetFcpTargetMapping_IN
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - hbapiwmi.h
api_name:
 - _GetFcpTargetMapping_IN
 - PGetFcpTargetMapping_IN
 - GetFcpTargetMapping_IN
---

# _GetFcpTargetMapping_IN structure


## -description

The GetFcpTargetMapping_IN structure is used to report the output parameter data of the <a href="/windows-hardware/drivers/storage/getfcptargetmapping">GetFcpTargetMapping</a> WMI method to the WMI client.

## -struct-fields

### -field HbaPortWWN

Contains a worldwide name for the port whose table of mappings is to be retrieved.

### -field InEntryCount

Indicates the total number of persistent bindings associated with the HBA.

## -remarks

The <a href="/windows-hardware/drivers/storage/getfcptargetmapping">GetFcpTargetMapping</a> WMI method queries a WMI provider for mappings between the information that uniquely identifies a set of logical units for the operating system and the fibre channel protocol (FCP) identifiers for the logical units.

The WMI tool suite generates a declaration of the GetFcpTargetMapping_IN structure in <i>Hbapiwmi.h </i>when it compiles the <a href="/windows-hardware/drivers/storage/msfc-hbafcpinfo-wmi-class">MSFC_HBAFCPInfo WMI Class</a>.

## -see-also

<a href="/windows-hardware/drivers/storage/getfcptargetmapping">GetFcpTargetMapping</a>



<a href="/windows-hardware/drivers/storage/msfc-hbafcpinfo-wmi-class">MSFC_HBAFCPInfo WMI Class</a>

