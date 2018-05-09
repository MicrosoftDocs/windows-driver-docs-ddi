---
UID: NF:hbaapi.HBA_SendCTPassThru
title: HBA_SendCTPassThru function
author: windows-driver-content
description: The HBA_SendCTPassThru routine sends a common transport (CT) pass-through command.
old-location: storage\hba_sendctpassthru.htm
old-project: storage
ms.assetid: adfdb968-5ba3-43af-899a-7172c9ecf46c
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: HBA_SendCTPassThru, HBA_SendCTPassThru routine [Storage Devices], fibreHBA_rtns_cae90bb3-cdb2-47fe-92b8-e2bffefa338d.xml, hbaapi/HBA_SendCTPassThru, storage.hba_sendctpassthru
ms.prod: windows-hardware
ms.technology: windows-devices
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
-	HBA_SendCTPassThru
product:
- Windows
targetos: Windows
req.typenames: 
---

# HBA_SendCTPassThru function


## -description


The <b>HBA_SendCTPassThru</b> routine sends a common transport (CT) pass-through command. 


## -parameters




### -param Handle

TBD


### -param pReqBuffer [in]

Pointer to a buffer that contains the full frame of the common transport command in big-endian (wire) format.


### -param ReqBufferSize [in]

Indicates the size of the buffer pointed to by <i>pReqBuffer</i>:


### -param pRspBuffer [out]

Pointer to a buffer that contains the payload data from the reply to the common transport command in big-endian (wire) format. 


### -param RspBufferSize [in]

Indicates the size of the buffer pointed to by <i>pRspBuffer</i>. 


#### - HbaHandle [in]

Contains a value returned by the routine <a href="https://msdn.microsoft.com/library/windows/hardware/ff557097">HBA_OpenAdapter</a> that identifies the HBA that will route the CT command. The HBA routes the CT command to the server that runs the service requested by the CT command. 


## -returns



The <b>HBA_SendCTPassThru</b> routine returns a value of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff557233">HBA_STATUS</a> that indicates the status of the HBA. If the HBA successfully delivers the command to the destination service, and the service executes the command and successfully returns the results, the HBA_SendCTPassThru routine returns a value of HBA_STATUS_OK. If the command does not succeed, this routine returns an appropriate error code of type HBA_STATUS.




## -remarks



The <b>HBA_SendCTPassThru</b> library routine serves a purpose very similar to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff565409">SendCTPassThru</a> WMI method. 

A CT command can request services that distribute encryption keys, IP addresses, time stamps, names, aliases, fabric configuration, and security policies. For a complete list of the service types that can be specified in a CT command, see the <i>Fibre Channel Generic Services - 4 (FC-GS-4)</i> specification published by the ANSI committee. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff557097">HBA_OpenAdapter</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff557233">HBA_STATUS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff557209">HBA_SendCTPassThruV2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff565409">SendCTPassThru</a>
 

 

