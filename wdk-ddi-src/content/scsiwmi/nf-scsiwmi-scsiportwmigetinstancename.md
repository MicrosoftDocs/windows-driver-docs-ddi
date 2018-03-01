---
UID: NF:scsiwmi.ScsiPortWmiGetInstanceName
title: ScsiPortWmiGetInstanceName function
author: windows-driver-content
description: The ScsiPortWmiGetInstanceName routine returns a pointer to the instance name associated with the indicated the Windows Management Instrumentation (WMI) SCSI Request Block (SRB).
old-location: storage\scsiportwmigetinstancename.htm
old-project: storage
ms.assetid: ff2ebd1c-d0ac-47a7-90d4-0b49259784c1
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: ScsiPortWmiGetInstanceName, ScsiPortWmiGetInstanceName routine [Storage Devices], scsiprt_184c6508-4189-4ab2-a445-7e52e5c688ab.xml, scsiwmi/ScsiPortWmiGetInstanceName, storage.scsiportwmigetinstancename
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: scsiwmi.h
req.include-header: Miniport.h, Scsi.h
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	scsiwmi.h
api_name:
-	ScsiPortWmiGetInstanceName
product: Windows
targetos: Windows
req.typenames: SCSIWMI_ENABLE_DISABLE_CONTROL
req.product: Windows 10 or later.
---

# ScsiPortWmiGetInstanceName function


## -description


The <b>ScsiPortWmiGetInstanceName</b> routine returns a pointer to the instance name associated with the indicated the <a href="https://msdn.microsoft.com/5c2ed322-0fc9-4004-9a5f-f4d3c6a59fe9">Windows Management Instrumentation</a> (WMI) SCSI Request Block (SRB). 
<div class="alert"><b>Note</b>  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## -syntax


````
PWCHAR ScsiPortWmiGetInstanceName(
  _In_ PSCSIWMI_REQUEST_CONTEXT RequestContext
);
````


## -parameters




### -param RequestContext [in]

Pointer to a structure of type <a href="..\scsiwmi\ns-scsiwmi-scsiwmi_request_context.md">SCSIWMI_REQUEST_CONTEXT</a> that contains the request context for a WMI SRB. 


## -returns



Pointer to a counted string containing the instance name associated with the indicated SRB.  If the SRB type is one that does not use an instance name, <b>ScsiPortWmiGetInstanceName</b> returns <b>NULL</b>. 




## -remarks



The parameter <b>RequestContext</b> points to a request context structure, <a href="..\scsiwmi\ns-scsiwmi-scsiwmi_request_context.md">SCSIWMI_REQUEST_CONTEXT</a>, that contains information associated with a <a href="https://msdn.microsoft.com/5c2ed322-0fc9-4004-9a5f-f4d3c6a59fe9">Windows Management Instrumentation</a> (WMI) SCSI request block (SRB). The request context structure, in turn, contains one of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff566371">WMI WNODE_XXX Structures</a> that is used by the WMI system to pass data between user-mode data consumers and kernel-mode data providers such as drivers. 

The WNODE_XXX structure contained in the request context holds an instance name associated with the WMI SRB. The miniport driver calls <b>ScsiPortWmiGetInstanceName</b> to extract this instance name from the request context. 

The memory allocated for the request context must remain valid until after the miniport driver calls <b>ScsiPortWmiPostProcess</b>, and <b>ScsiPortWmiPostProcess</b> returns the final SRB status and buffer size. If the SRB can pend, the memory for the request context should be allocated from the SRB extension. If the SRB cannot pend, the memory can be allocated from a stack frame that does not go out of scope.




## -see-also

<a href="..\scsiwmi\ns-scsiwmi-scsiwmi_request_context.md">SCSIWMI_REQUEST_CONTEXT</a>



<a href="..\wmistr\ns-wmistr-tagwnode_all_data.md">WNODE_ALL_DATA</a>



<a href="..\wmistr\ns-wmistr-tagwnode_single_instance.md">WNODE_SINGLE_INSTANCE</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20ScsiPortWmiGetInstanceName routine%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

