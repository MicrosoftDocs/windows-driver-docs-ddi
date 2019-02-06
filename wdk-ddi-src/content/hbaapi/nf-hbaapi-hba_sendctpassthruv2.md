---
UID: NF:hbaapi.HBA_SendCTPassThruV2
title: HBA_SendCTPassThruV2 function (hbaapi.h)
description: The HBA_SendCTPassThruV2 routine sends a common transport (CT) pass-through command through the indicated port.
old-location: storage\hba_sendctpassthruv2.htm
tech.root: storage
ms.assetid: 95526c2d-19bf-4f4a-abfa-e5be73c1a6a5
ms.date: 03/29/2018
ms.keywords: HBA_SendCTPassThruV2, HBA_SendCTPassThruV2 routine [Storage Devices], fibreHBA_rtns_8ed894f5-3f6c-4b71-a149-8e5624643aa0.xml, hbaapi/HBA_SendCTPassThruV2, storage.hba_sendctpassthruv2
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
-	HBA_SendCTPassThruV2
product:
- Windows
targetos: Windows
req.typenames: 
---

# HBA_SendCTPassThruV2 function


## -description


The <b>HBA_SendCTPassThruV2</b> routine sends a common transport (CT) pass-through command through the indicated port. 


## -parameters




### -param Handle

<p>Contains a value returned by the routine <a href="https://msdn.microsoft.com/library/Ff557097(v=VS.85).aspx"><b>HBA_OpenAdapter</b></a> that identifies the HBA that will route the CT command. The HBA routes the CT command to the server that runs the service requested by the CT command. </p>


### -param HbaPortWWN [in]

Contains the worldwide name (WWN) of the port from which to issue the command. For a definition of worldwide names, see the T11 committee's specification for <i>Fibre Channel HBA API</i>. 


### -param pReqBuffer [in]

Pointer to a buffer that contains the full frame of the common transport command in big-endian format.


### -param ReqBufferSize [in]

Indicates the size of the buffer pointed to by <i>pReqBuffer</i>:


### -param pRspBuffer [out]

Pointer to a buffer that contains the payload data from the reply to the common transport command in big-endian (wire) format. 


### -param pRspBufferSize

<p>On input, indicates the size, in bytes, of the buffer pointed to by <i>pRspBuffer</i>. On return, this member indicates the size, in bytes, of the response data. </p>




## -returns



The <b>HBA_SendCTPassThruV2</b> routine returns a value of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff557233">HBA_STATUS</a> that indicates the status of the HBA. If the HBA successfully delivers the command to the destination service, and the service executes the command and successfully returns the results, the HBA_SendCTPassThru routine returns a value of HBA_STATUS_OK. If the command does not succeed, this routine returns an appropriate error code of type HBA_STATUS.




## -remarks



The <b>HBA_SendCTPassThruV2</b> library routine is identical to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff557207">HBA_SendCTPassThru</a> routine, except that <b>HBA_SendCTPassThruV2</b> allows the caller to specify the port through which the CT command will be issued. 

The <b>HBA_SendCTPassThruV2</b> library routine serves a purpose very similar to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff565409">SendCTPassThru</a> WMI method. 

A CT command can request services that distribute encryption keys, IP addresses, time stamps, names, aliases, fabric configuration, and security policies. For a complete list of the service types that can be specified in a CT command, see the <i>Fibre Channel Generic Services - 4 (FC-GS-4)</i> specification published by the ANSI committee. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff557097">HBA_OpenAdapter</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff557233">HBA_STATUS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff557207">HBA_SendCTPassThru</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff565409">SendCTPassThru</a>
 

 

