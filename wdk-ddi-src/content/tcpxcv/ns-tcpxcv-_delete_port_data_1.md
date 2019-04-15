---
UID: NS:tcpxcv._DELETE_PORT_DATA_1
title: _DELETE_PORT_DATA_1 (tcpxcv.h)
description: The XcvData function uses a DELETE_PORT_DATA_1 structure when it deletes a port.
old-location: print\delete_port_data_1.htm
tech.root: print
ms.assetid: d4fb5bf9-7982-4abd-91ba-59b7798a18c7
ms.date: 04/20/2018
ms.keywords: "*PDELETE_PORT_DATA_1, DELETE_PORT_DATA_1, DELETE_PORT_DATA_1 structure [Print Devices], PDELETE_PORT_DATA_1, PDELETE_PORT_DATA_1 structure pointer [Print Devices], _DELETE_PORT_DATA_1, print.delete_port_data_1, spoolfnc_238080f3-e916-4a7f-9531-361659c21a3d.xml, tcpxcv/DELETE_PORT_DATA_1, tcpxcv/PDELETE_PORT_DATA_1"
ms.topic: struct
req.header: tcpxcv.h
req.include-header: Tcpxcv.h
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
- tcpxcv.h
api_name:
- DELETE_PORT_DATA_1
product:
- Windows
targetos: Windows
req.typenames: DELETE_PORT_DATA_1, *PDELETE_PORT_DATA_1
---

# _DELETE_PORT_DATA_1 structure


## -description


The <a href="https://msdn.microsoft.com/library/windows/hardware/ff564255">XcvData</a> function uses a DELETE_PORT_DATA_1 structure when it deletes a port.


## -struct-fields




### -field psztPortName

Specifies the name of the port to be deleted. The MAX_PORTNAME_LEN constant is defined in tcpxcv.h.


### -field Reserved

Is reserved for system use.


### -field dwVersion

Specifies the version of this structure, which is currently 1.


### -field dwReserved

Is obsolete, and must be set to 0.


## -remarks



When the <a href="https://msdn.microsoft.com/library/windows/hardware/ff564255">XcvData</a> function is called to delete a port, its <i>pInputData</i> parameter must be set with the address of a DELETE_PORT_DATA_1 structure. Set this function's <i>pszDataName</i> parameter to the string L"DeletePort". 

See <a href="https://msdn.microsoft.com/7b2b1cff-ab8f-44e0-9327-dc60a0072bf5">TCPMON Xcv Interface</a> for more information.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff564255">XcvData</a>
 

 

