---
UID: NS:d4drvif._DOT4_DC_CREATE_DATA
title: _DOT4_DC_CREATE_DATA (d4drvif.h)
description: Defines the DOT4_DC_CREATE_DATA construct.
old-location: print\dot4_dc_create_data.htm
tech.root: print
ms.assetid: 9C21732B-0AB1-4F3E-8F3D-F0B12007920A
ms.date: 04/20/2018
ms.keywords: "*PDOT4_DC_CREATE_DATA, DOT4_DC_CREATE_DATA, DOT4_DC_CREATE_DATA structure [Print Devices], PDOT4_DC_CREATE_DATA, PDOT4_DC_CREATE_DATA structure pointer [Print Devices], _DOT4_DC_CREATE_DATA, d4drvif/DOT4_DC_CREATE_DATA, d4drvif/PDOT4_DC_CREATE_DATA, print.dot4_dc_create_data"
f1_keywords:
 - "d4drvif/DOT4_DC_CREATE_DATA"
req.header: d4drvif.h
req.include-header: 
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- D4drvif.h
api_name:
- DOT4_DC_CREATE_DATA
product:
- Windows
targetos: Windows
req.typenames: DOT4_DC_CREATE_DATA, *PDOT4_DC_CREATE_DATA
---

# _DOT4_DC_CREATE_DATA structure


## -description


Defines the <b>DOT4_DC_CREATE_DATA</b> construct.


## -struct-fields




### -field bPsid

Specifies this or the service name sent.


### -field pServiceName

Describes the <b>CHAR</b>  member <b>pServiceName</b>.


### -field bType

Specifies the type, stream or packet, of channels on the socket.


### -field ulBufferSize

Specifies the size of the read buffer for channels on socket.


### -field usMaxHtoPPacketSize

Describes the <b>USHORT</b> member <b>usMaxHtoPPacketSize</b>.


### -field usMaxPtoHPacketSize

Describes the <b>USHORT</b> member <b>usMaxPtoHPacketSize</b>.


### -field bHsid

Specifies the host socket ID returned.

