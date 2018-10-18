---
UID: NF:hbaapi.HBA_SendRNIDV2
title: HBA_SendRNIDV2 function
author: windows-driver-content
description: The HBA_SendRNIDV2 routine sends a request for node identification data (RNID) to the indicated HBA, which in turn routes the request through the indicated port or node to the appropriate fabric configuration server.
old-location: storage\hba_sendrnidv2.htm
tech.root: storage
ms.assetid: c46aee6e-f31d-4b8d-8244-3c364aa79ae4
ms.date: 03/29/2018
ms.keywords: HBA_SendRNIDV2, HBA_SendRNIDV2 routine [Storage Devices], fibreHBA_rtns_8e5796fe-6cfa-42e8-9855-9ab89752bfec.xml, hbaapi/HBA_SendRNIDV2, storage.hba_sendrnidv2
ms.topic: function
req.header: hbaapi.h
req.include-header: Hbaapi.h
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
req.lib: Hbaapi.lib
req.dll: Hbaapi.dll
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	Hbaapi.dll
api_name:
-	HBA_SendRNIDV2
product:
- Windows
targetos: Windows
req.typenames: 
---

# HBA_SendRNIDV2 function


## -description


The <b>HBA_SendRNIDV2</b> routine sends a request for node identification data (RNID) to the indicated HBA, which in turn routes the request through the indicated port or node to the appropriate fabric configuration server. 


## -parameters




### -param Handle

<p>Contains a value returned by the routine <a href="https://msdn.microsoft.com/library/Ff557097(v=VS.85).aspx"><b>HBA_OpenAdapter</b></a> that identifies the HBA that will route the command. The HBA routes this command through the port specified by <i>hbaPortWWN </i>to the port specified by <i>destWWN </i>on the appropriate fabric configuration server. </p>


### -param HbaPortWWN

<p>Contains a 64-bit worldwide name (WWN) that uniquely identifies a port from which the RNID command is issued. For a discussion of worldwide names, see the T11 committee's <i>Fibre Channel HBA API</i> specification. </p>


### -param DestWWN

<p>Contains a WWN for the destination port on the fabric configuration server that will provide the node identification data. </p>


### -param DestFCID

<p>Contains the fibre channel identifier of the destination port specified by <i>destWWN. </i>If no fibre channel identifier for the destination port is available, the caller should set this member to 0. </p>


### -param NodeIdDataFormat [in]

Contains a number that indicates the node identification format. For a complete description of the allowed formats and the numbers that identify each format, see the <i>Fibre Channel Generic Services - 4 (FC-GS-4)</i> specification published by the ANSI committee.


### -param pRspBuffer [out]

Pointer to a buffer that contains the payload data, in big-endian (wire) format, from the reply to the node identification request.  


### -param pRspBufferSize

<p>On input, indicates the size, in bytes, of the buffer pointed to by <i>pRspBuffer</i>. On return, this member indicates the size, in bytes, of the response data. </p>




## -returns



The <b>HBA_SendRNIDV2</b> routine returns a value of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff557233">HBA_STATUS</a> that indicates the status of the HBA.




## -remarks



The node identification data request is a common transport (CT) command that queries a fabric configuration server for node identification data. For a complete description of this command, see the sections dealing with node identification requests in the <i>Fibre Channel Generic Services - 4 (FC-GS-4)</i> specification published by the ANSI committee.

The <b>HBA_SendRNIDV2</b> library routine serves a purpose very similar to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff565459">SendRNID</a> WMI method. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff557097">HBA_OpenAdapter</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff557216">HBA_SendRNID</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff565459">SendRNID</a>
 

 

