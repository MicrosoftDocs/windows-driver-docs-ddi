---
UID: NS:bdatypes._BDA_PROGRAM_PID_LIST
title: _BDA_PROGRAM_PID_LIST (bdatypes.h)
description: The BDA_PROGRAM_PID_LIST structure describes data of a specific program to view. This data consists of packets that are identified with packet identifiers (PID).
old-location: stream\bda_program_pid_list.htm
tech.root: stream
ms.assetid: d3a96377-71f9-40ba-a15f-cacd64dcc6c4
ms.date: 04/23/2018
ms.keywords: "*PBDA_PROGRAM_PID_LIST, BDA_PROGRAM_PID_LIST, BDA_PROGRAM_PID_LIST structure [Streaming Media Devices], PBDA_PROGRAM_PID_LIST, PBDA_PROGRAM_PID_LIST structure pointer [Streaming Media Devices], _BDA_PROGRAM_PID_LIST, bdaref_a78db54e-c75e-46dc-8b81-f97163569450.xml, bdatypes/BDA_PROGRAM_PID_LIST, bdatypes/PBDA_PROGRAM_PID_LIST, stream.bda_program_pid_list"
ms.topic: struct
req.header: bdatypes.h
req.include-header: Bdatypes.h
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
- bdatypes.h
api_name:
- BDA_PROGRAM_PID_LIST
product:
- Windows
targetos: Windows
req.typenames: BDA_PROGRAM_PID_LIST, *PBDA_PROGRAM_PID_LIST
---

# _BDA_PROGRAM_PID_LIST structure


## -description


The BDA_PROGRAM_PID_LIST structure describes data of a specific program to view. This data consists of packets that are identified with packet identifiers (PID). 


## -struct-fields




### -field ulProgramNumber

Number of the program to be viewed. 


### -field ulcPIDs

Number of PIDs in the <b>ulPID</b> array. 


### -field ulPID

Array of PIDs that identify packets of program data. 


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/stream/ksproperty-bda-ca-set-program-pids">KSPROPERTY_BDA_CA_SET_PROGRAM_PIDS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/stream/kspropsetid-bdaca">KSPROPSETID_BdaCA</a>
 

 

