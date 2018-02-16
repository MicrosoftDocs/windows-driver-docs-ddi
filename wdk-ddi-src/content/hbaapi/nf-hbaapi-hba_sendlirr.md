---
UID: NF:hbaapi.HBA_SendLIRR
title: HBA_SendLIRR function
author: windows-driver-content
description: The HBA_SendLIRR routine registers or de-registers a local (source) port to receive link incident records (LIR) from a remote (destination) port.
old-location: storage\hba_sendlirr.htm
old-project: storage
ms.assetid: 2e38d297-1e26-4605-a242-3f0180ac0360
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: HBA_SendLIRR routine [Storage Devices], storage.hba_sendlirr, HBA_SendLIRR, hbaapi/HBA_SendLIRR, fibreHBA_rtns_c9e05691-f605-4946-bb8c-ab317464523a.xml
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	Hbaapi.dll
apiname:
-	HBA_SendLIRR
product: Windows
targetos: Windows
req.typenames: HBA_WWNTYPE
---

# HBA_SendLIRR function


## -description


The <b>HBA_SendLIRR</b> routine registers or de-registers a local (source) port to receive link incident records (LIR) from a remote (destination) port.


## -syntax


````
HBA_STATUS HBA_API HBA_SendLIRR(
  _In_    HBA_HANDLE Handle,
  _In_    HBA_WWN    SourceWWN,
  _In_    HBA_WWN    DestWWN,
  _In_    HBA_UINT8  Function,
  _In_    HBA_UINT8  Type,
  _Out_   void       *pRspBuffer,
  _Inout_ HBA_UINT32 *RspBufferSize
);
````


## -parameters




### -param Handle [in]

Contains a value returned by the routine <a href="..\hbaapi\nf-hbaapi-hba_openadapter.md">HBA_OpenAdapter</a> that identifies the HBA through which to send the LIR request. 


### -param SourceWWN [in]

Contains the worldwide name (WWN) of the local port from which to issue the command and which will receive link incident records from the destination port referenced by <i>DestWWN</i>. For a definition of worldwide names, see the T11 committee's specification for <i>Fibre Channel HBA API</i>. 


### -param DestWWN [in]

Contains the WWN of the remote destination port that will report link incident records to the source port. For a definition of worldwide names, see the T11 committee's specification for <i>Fibre Channel HBA API</i>. 


### -param Function [in]

Specifies the action to take. This member either registers a source port to receive link incident records and specifies the mode of registration, or it de-registers a source port that is already registered. This member must have one of the following values.

<table>
<tr>
<th>Value in Hexadecimal</th>
<th>Meaning</th>
</tr>
<tr>
<td>
0x0

</td>
<td>
Reserved.

</td>
</tr>
<tr>
<td>
0x01

</td>
<td>
Indicates that the registration is conditional. The source port is added to the registration list for records with the format indicated in <i>Type</i> and receives link incident records of that type only if no other ports are receiving records for that type. 

</td>
</tr>
<tr>
<td>
0x02

</td>
<td>
Indicates that the source port is always added to the registration list for records with the format indicated in <i>Type</i>. 

</td>
</tr>
<tr>
<td>
0x03

</td>
<td>
Reserved. 

</td>
</tr>
<tr>
<td>
0xff

</td>
<td>
Indicates that the source port is removed from the registration list for records with the format indicated in <i>Type</i> and no longer receives link incident records of that format type. 

</td>
</tr>
</table>
 

For further explanation of the available registration modes, see the T11 committee's <i>Fibre Channel Framing and Signaling</i> specification.


### -param Type [in]

Specifies the type of records whose delivery is affected by the link incident record request (LIRR). When 0, the LIRR governs the delivery of common link incident records, so if the source port is registering to receive records, then the source port is added to the destination port's registration list for common link incident records. If the source port is de-registering, then it is removed from that list. 

If <i>Type </i>is nonzero, then it specifies the format type of the records for which the source port is registering or de-registering. For a list of the types of formats and their corresponding values, see the FC-4 type codes table in the T11 committee's <i>Fibre Channel Framing and Signaling</i> specification. 


### -param pRspBuffer [out]

Pointer to a buffer that receives the payload data of the response to the LIRR, if the LIRR succeeds. If the destination port rejects the request, this buffer holds the link service reject (LS_RJT) payload data. If the amount of returned data exceeds the buffer size specified in <i>RspBufferSize</i>, the data is truncated to the buffer size<i>. </i>The payload data is in big-endian format (higher order bytes are in lower addresses). 


### -param pRspBufferSize

TBD




#### - RspBufferSize [in, out]

On input, indicates the size, in bytes, of the buffer at <i>pRspBuffer</i>. On output, this member indicates the size, in bytes, of the response data. Eight bytes is sufficient for any response.


## -returns



The <b>HBA_ScsiReportLUNsV2</b> routine returns a value of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff557233">HBA_STATUS</a> that indicates the status of the HBA. In particular, <b>HBA_ScsiReportLUNsV2</b> returns one of the following values.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>HBA_STATUS_OK</b></dt>
</dl>
</td>
<td width="60%">
Returned if the LIRR succeeded and payload data was successfully retrieved. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>HBA_STATUS_ERROR_ILLEGAL_WWN</b></dt>
</dl>
</td>
<td width="60%">
Returned if the HBA referenced by <i>handle</i> does not contain a port with a name that matches <i>SourceWWN</i>. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>HBA_STATUS_ERROR_NOT_SUPPORTED</b></dt>
</dl>
</td>
<td width="60%">
Returned if the local HBA referenced by <i>handle </i>does not support link incident reporting.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>HBA_STATUS_ERROR_ELS_REJECT</b></dt>
</dl>
</td>
<td width="60%">
Returned if the destination port referenced by <i>DestWWN </i>rejected the request node identification information data (RNID) that identifies the source HBA. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>HBA_STATUS_ERROR</b></dt>
</dl>
</td>
<td width="60%">
Returned if an unspecified error occurred that prevented the execution of the LIR request. 

</td>
</tr>
</table>
 




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff557233">HBA_STATUS</a>



<a href="..\hbaapi\nf-hbaapi-hba_openadapter.md">HBA_OpenAdapter</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20HBA_SendLIRR routine%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

