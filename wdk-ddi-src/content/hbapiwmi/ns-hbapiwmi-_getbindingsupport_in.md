---
UID: NS:hbapiwmi._GetBindingSupport_IN
title: _GetBindingSupport_IN (hbapiwmi.h)
description: The GetBindingSupport_IN structure is used by a WMI client to deliver the input parameter data of the GetBindingSupport WMI method to the HBA miniport driver.
old-location: storage\getbindingsupport_in.htm
tech.root: storage
ms.date: 03/29/2018
keywords: ["GetBindingSupport_IN structure"]
ms.keywords: "*PGetBindingSupport_IN, GetBindingSupport_IN, GetBindingSupport_IN structure [Storage Devices], PGetBindingSupport_IN, PGetBindingSupport_IN structure pointer [Storage Devices], _GetBindingSupport_IN, hbapiwmi/GetBindingSupport_IN, hbapiwmi/PGetBindingSupport_IN, storage.getbindingsupport_in, structs-Fibre_858abc05-6d3e-4630-a9f9-4b9aa742ea8e.xml"
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
req.typenames: GetBindingSupport_IN, *PGetBindingSupport_IN
f1_keywords:
 - _GetBindingSupport_IN
 - hbapiwmi/_GetBindingSupport_IN
 - PGetBindingSupport_IN
 - hbapiwmi/PGetBindingSupport_IN
 - GetBindingSupport_IN
 - hbapiwmi/GetBindingSupport_IN
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - hbapiwmi.h
api_name:
 - GetBindingSupport_IN
---

# _GetBindingSupport_IN structure


## -description

The GetBindingSupport_IN structure is used by a WMI client to deliver the input parameter data of the <a href="/windows-hardware/drivers/storage/getbindingsupport">GetBindingSupport</a> WMI method to the HBA miniport driver.

## -struct-fields

### -field PortWWN

Contains a worldwide name that indicates the port whose persistent bindings are to be retrieved.

## -remarks

The WMI tool suite generates a declaration of the GetBindingSupport_IN structure in <i>Hbapiwmi.h </i>when it compiles the <a href="/windows-hardware/drivers/storage/msfc-hbafcpinfo-wmi-class">MSFC_HBAFCPInfo WMI Class</a>.

## -see-also

<a href="/windows-hardware/drivers/storage/getbindingsupport">GetBindingSupport</a>
