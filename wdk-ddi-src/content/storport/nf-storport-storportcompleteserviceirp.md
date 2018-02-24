---
UID: NF:storport.StorPortCompleteServiceIrp
title: StorPortCompleteServiceIrp function
author: windows-driver-content
description: The StorPortCompleteServiceIrp routine is called by a Storport virtual miniport driver when it needs to complete a request that it received in its HwStorProcessServiceRequest callback routine.
old-location: storage\storportcompleteserviceirp.htm
old-project: storage
ms.assetid: 359b1096-f987-4884-ab67-2290bf5196b5
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: storprt_439990ea-8133-4114-b417-1c88e53cce14.xml, StorPortCompleteServiceIrp routine [Storage Devices], storage.storportcompleteserviceirp, StorPortCompleteServiceIrp, storport/StorPortCompleteServiceIrp
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: storport.h
req.include-header: Storport.h
req.target-type: Universal
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	storport.h
apiname:
-	StorPortCompleteServiceIrp
product: Windows
targetos: Windows
req.typenames: STOR_SPINLOCK
req.product: Windows 10 or later.
---

# StorPortCompleteServiceIrp function


## -description


The <b>StorPortCompleteServiceIrp</b> routine is called by a Storport virtual miniport driver when it needs to complete a request that it received in its <a href="https://msdn.microsoft.com/library/windows/hardware/ff557410">HwStorProcessServiceRequest</a> callback routine.


## -syntax


````
ULONG StorPortCompleteServiceIrp(
  _In_ PVOID HwDeviceExtension,
  _In_ PVOID Irp
);
````


## -parameters




### -param HwDeviceExtension [in]

A pointer to the hardware device extension. This is a per HBA storage area that the port driver allocates and initializes on behalf of the miniport driver. Miniport drivers usually store HBA-specific information in this extension, such as the state of the HBA and the  mapped access ranges for the HBA. This area is available to the miniport driver immediately after the miniport driver calls <a href="..\storport\nf-storport-storportinitialize.md">StorPortInitialize</a>. The port driver frees this memory when it removes the device. 


### -param Irp [in]

A pointer to the I/O request.


## -returns



<b>StorPortCompleteServiceIrp</b> returns one of the following values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STOR_STATUS_NOT_IMPLEMENTED</b></dt>
</dl>
</td>
<td width="60%">
This function is not implemented on the active operating system.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STOR_STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
Indicates that the routine completed the request successfully.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STOR_STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
The Irp that was passed was <b>NULL</b>.

</td>
</tr>
</table>
 




## -remarks



The Storport virtual miniport driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff557410">HwStorProcessServiceRequest</a> callback routine receives an IRP that is produced by an IOCTL when a caller, such as a user-mode application or kernel-mode driver, requires a reverse callback operation. The I/O is completed by the miniport driver by calling the <b>StorPortCompleteServiceIrp</b> routine when it needs to tell the caller of something or needs the caller to do something.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff557410">HwStorProcessServiceRequest</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20StorPortCompleteServiceIrp routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

