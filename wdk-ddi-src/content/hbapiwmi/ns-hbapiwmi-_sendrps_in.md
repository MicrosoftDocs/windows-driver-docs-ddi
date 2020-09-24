---
UID: NS:hbapiwmi._SendRPS_IN
title: _SendRPS_IN (hbapiwmi.h)
description: The SendRPS_IN structure is used to deliver input parameter data to the SendRPS WMI method.
old-location: storage\sendrps_in.htm
tech.root: storage
ms.assetid: 7ab8986d-1e28-4d25-888f-cd10e310d623
ms.date: 03/29/2018
keywords: ["SendRPS_IN structure"]
ms.keywords: "*PSendRPS_IN, PSendRPS_IN, PSendRPS_IN structure pointer [Storage Devices], SendRPS_IN, SendRPS_IN structure [Storage Devices], _SendRPS_IN, hbapiwmi/PSendRPS_IN, hbapiwmi/SendRPS_IN, storage.sendrps_in, structs-Fibre_52ab21d3-f6bf-4e1d-b5a7-3f9cd054038c.xml"
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
req.typenames: SendRPS_IN, *PSendRPS_IN
f1_keywords:
 - _SendRPS_IN
 - hbapiwmi/_SendRPS_IN
 - PSendRPS_IN
 - hbapiwmi/PSendRPS_IN
 - SendRPS_IN
 - hbapiwmi/SendRPS_IN
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - hbapiwmi.h
api_name:
 - SendRPS_IN
---

# _SendRPS_IN structure


## -description

The SendRPS_IN structure is used to deliver input parameter data to the <a href="/windows-hardware/drivers/storage/sendrps">SendRPS</a> WMI method.

## -struct-fields

### -field PortWWN

Contains a worldwide name for the local port through which the RPS command is sent.

### -field AgentWWN

Contains a worldwide name for the port that is to be queried for the status of the port indicated by <b>ObjectWWN</b>.

### -field ObjectWWN

Contains the worldwide name of the port for which port status is to be returned.

### -field AgentDomain

Contains the domain number of the domain controller to be queried for the status of the port indicated by <b>ObjectWWN</b>.

### -field ObjectPortNumber

Contains the worldwide name of the port for which port status is to be returned.

## -remarks

The WMI tool suite generates a declaration of the SendRPS_IN structure in <i>Hbapiwmi.h </i>when it compiles the <a href="/windows-hardware/drivers/storage/msfc-hbaadaptermethods-wmi-class">MSFC_HBAAdapterMethods WMI Class</a>.

## -see-also

<a href="/windows-hardware/drivers/storage/sendrps">SendRPS</a>