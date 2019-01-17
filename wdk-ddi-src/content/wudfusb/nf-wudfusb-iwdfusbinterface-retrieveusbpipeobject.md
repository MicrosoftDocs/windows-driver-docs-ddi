---
UID: NF:wudfusb.IWDFUsbInterface.RetrieveUsbPipeObject
title: IWDFUsbInterface::RetrieveUsbPipeObject
description: The RetrieveUsbPipeObject method retrieves a USB pipe object for the specified pipe index.
old-location: wdf\iwdfusbinterface_retrieveusbpipeobject.htm
tech.root: wdf
ms.assetid: abfaad6b-be42-4547-aa26-5b44e53118bc
ms.date: 02/26/2018
ms.keywords: IWDFUsbInterface interface,RetrieveUsbPipeObject method, IWDFUsbInterface.RetrieveUsbPipeObject, IWDFUsbInterface::RetrieveUsbPipeObject, RetrieveUsbPipeObject, RetrieveUsbPipeObject method, RetrieveUsbPipeObject method,IWDFUsbInterface interface, UMDFUSBref_84f2ac72-965e-4fd4-a127-f153a5fc54f7.xml, umdf.iwdfusbinterface_retrieveusbpipeobject, wdf.iwdfusbinterface_retrieveusbpipeobject, wudfusb/IWDFUsbInterface::RetrieveUsbPipeObject
ms.topic: method
req.header: wudfusb.h
req.include-header: Wudfusb.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 1.5
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: Unavailable in UMDF 2.0 and later.
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: WUDFx.dll
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	WUDFx.dll
api_name:
-	IWDFUsbInterface.RetrieveUsbPipeObject
product:
- Windows
targetos: Windows
req.typenames: 
---

# IWDFUsbInterface::RetrieveUsbPipeObject


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>RetrieveUsbPipeObject</b> method retrieves a USB pipe object for the specified pipe index.


## -parameters




### -param PipeIndex [in]

The index of the USB pipe object to retrieve.


### -param ppPipe [out]

A pointer to a variable that receives a pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff560391">IWDFUsbTargetPipe</a> interface for the USB pipe object whose index is specified by <i>PipeIndex</i>.


## -returns



<b>RetrieveUsbPipeObject</b> returns one of the following values: 

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>S_OK </b></dt>
</dl>
</td>
<td width="60%">

<a href="https://msdn.microsoft.com/abfaad6b-be42-4547-aa26-5b44e53118bc">RetrieveUsbPipeObject</a> successfully retrieved the USB pipe object. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_OUTOFMEMORY </b></dt>
</dl>
</td>
<td width="60%">

<a href="https://msdn.microsoft.com/abfaad6b-be42-4547-aa26-5b44e53118bc">RetrieveUsbPipeObject</a> encountered an allocation failure.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>An error code that is defined in Winerror.h</b></dt>
</dl>
</td>
<td width="60%">
This value corresponds to the error code that the WinUsb API returned.

</td>
</tr>
</table>
 




## -remarks



A UMDF driver can call the methods of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff560391">IWDFUsbTargetPipe</a> interface that the <b>RetrieveUsbPipeObject</b> method retrieves to obtain the type of pipe and other information.


#### Examples

For a code example of how to use the<b>RetrieveUsbPipeObject</b> method, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff560334">IWDFUsbInterface::GetNumEndPoints</a>.

<div class="code"></div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff560312">IWDFUsbInterface</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff560391">IWDFUsbTargetPipe</a>
 

 

