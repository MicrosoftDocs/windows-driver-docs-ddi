---
UID: NC:scsiwmi.PSCSIWMI_EXECUTE_METHOD
title: PSCSIWMI_EXECUTE_METHOD
author: windows-driver-content
description: A miniport driver's HwScsiWmiExecuteMethod routine is called to execute a method associated with a data block.
old-location: storage\hwscsiwmiexecutemethod.htm
old-project: storage
ms.assetid: 67a82442-591e-4e52-aaaf-b3cdb68c483a
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: storage.hwscsiwmiexecutemethod, HwScsiWmiExecuteMethod callback function [Storage Devices], HwScsiWmiExecuteMethod, PSCSIWMI_EXECUTE_METHOD, PSCSIWMI_EXECUTE_METHOD, scsiwmi/HwScsiWmiExecuteMethod, Scsimini_a0b3e943-a363-478d-9d68-09acf0c5b591.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: scsiwmi.h
req.include-header: Scsiwmi.h
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
req.lib: 
req.dll: 
req.irql: 
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	UserDefined
apilocation: 
-	scsiwmi.h
apiname: 
-	HwScsiWmiExecuteMethod
product: Windows
targetos: Windows
req.typenames: SCSISCAN_INFO, *PSCSISCAN_INFO
req.product: Windows 10 or later.
---

# PSCSIWMI_EXECUTE_METHOD callback


## -description


A miniport driver's <b>HwScsiWmiExecuteMethod</b> routine is called to execute a method associated with a data block. This routine is optional.
<div class="alert"><b>Note</b>  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## -prototype


````
BOOLEAN HwScsiWmiExecuteMethod(
  _In_    PVOID                    DeviceContext,
  _In_    PSCSIWMI_REQUEST_CONTEXT RequestContext,
  _In_    ULONG                    GuidIndex,
  _In_    ULONG                    InstanceIndex,
  _In_    ULONG                    MethodId,
  _In_    ULONG                    InBufferSize,
  _In_    ULONG                    OutBufferSize,
  _Inout_ PUCHAR                   Buffer
);
````


## -parameters




### -param DeviceContext [in]

Points to the miniport driver-defined context value passed to <a href="..\scsiwmi\nf-scsiwmi-scsiportwmidispatchfunction.md">ScsiPortWmiDispatchFunction</a>. 


### -param RequestContext [in]

Points to the SCSIWMI_REQUEST_CONTEXT structure that the miniport driver passed to <a href="..\scsiwmi\nf-scsiwmi-scsiportwmidispatchfunction.md">ScsiPortWmiDispatchFunction</a>. 


### -param GuidIndex [in]

Specifies the data block by its index into the list of GUIDs in the SCSI_WMILIB_CONTEXT structure that the miniport driver passed to <a href="..\scsiwmi\nf-scsiwmi-scsiportwmidispatchfunction.md">ScsiPortWmiDispatchFunction</a>. 


### -param InstanceIndex [in]

If the block specified by <i>GuidIndex</i> has multiple instances, <i>InstanceIndex</i> specifies the instance.


### -param MethodId [in]

Specifies the ID of the method to execute. The miniport driver defines the method ID as an item in a data block.


### -param InBufferSize [in]

Indicates the size in bytes of the input data. If there is no input data, <i>InBufferSize</i> is zero. 


### -param OutBufferSize [in]

Indicates the number of bytes available in the buffer for output data. 


### -param Buffer [in, out]

Points to a buffer that holds the input data and receives the output data, if any, from the method. If the buffer is too small to receive all of the output, the miniport driver calls <b>ScsiPortWmiPostProcess</b> with SRB_STATUS_DATA_OVERRUN and the size required.


## -returns


<b>HwScsiWmiExecuteMethod</b> returns SRB_STATUS_PENDING if the request is pending, or a nonzero SRB status value if the request was completed.  The SRB status value returned by this routine is the same as what was passed in to <a href="..\scsiwmi\nf-scsiwmi-scsiportwmipostprocess.md">ScsiPortWmiPostProcess</a>. Although the return value data type is BOOLEAN, the <b>HwScsiWmiExecuteMethod</b> routine actually returns an SRB status value.



## -remarks


When a miniport driver receives an SRB in which the <b>Function</b> member is set to SRB_FUNCTION_WMI, it calls <a href="..\scsiwmi\nf-scsiwmi-scsiportwmidispatchfunction.md">ScsiPortWmiDispatchFunction</a> with a pointer to an initialized SCSI_WMILIB_CONTEXT structure and <i>MinorFunction</i> set to <b>Srb-&gt;WmiSubFunction</b>. The SCSI port driver calls the miniport driver's <b>HwScsiWmiExecuteMethod</b> routine if <i>MinorFunction</i> indicates a request to execute a method.

If a miniport driver does not implement a <b>HwScsiWmiExecuteMethod</b> routine, it must set <b>ExecuteWmiMethod</b> to <b>NULL</b> in the SCSI_WMILIB_CONTEXT the miniport driver passes to <a href="..\scsiwmi\nf-scsiwmi-scsiportwmidispatchfunction.md">ScsiPortWmiDispatchFunction</a>. In this case, the port driver returns SRB_STATUS_ERROR to the caller.

If the method generates output, the miniport driver should check the size of the output buffer in <i>OutBufferSize</i> before performing any operation that might have side effects or that should not be performed twice. For example, if a method returns the values of a group of counters and then resets the counters, the miniport driver should check the buffer size before resetting the counters. This ensures that the port driver can safely resend the request with a larger buffer. If the buffer is too small, the miniport driver should call <a href="..\scsiwmi\nf-scsiwmi-scsiportwmipostprocess.md">ScsiPortWmiPostProcess</a> with SRB_STATUS_DATA_OVERRUN and the size of the output buffer needed to fulfill the request. 

The miniport driver executes the method and writes output, if any, to the buffer. Before returning from <b>HwScsiWmiExecuteMethod</b>, the miniport driver calls <a href="..\scsiwmi\nf-scsiwmi-scsiportwmipostprocess.md">ScsiPortWmiPostProcess</a> with an appropriate <i>SrbStatus</i> value and the number of bytes used in the output buffer.



## -see-also

<a href="..\scsiwmi\nf-scsiwmi-scsiportwmipostprocess.md">ScsiPortWmiPostProcess</a>

<a href="..\scsiwmi\ns-scsiwmi-scsiwmi_request_context.md">SCSIWMI_REQUEST_CONTEXT</a>

<a href="..\scsiwmi\ns-scsiwmi-_scsiwmilib_context.md">SCSI_WMILIB_CONTEXT</a>

<a href="..\scsiwmi\nf-scsiwmi-scsiportwmidispatchfunction.md">ScsiPortWmiDispatchFunction</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20HwScsiWmiExecuteMethod callback function%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

