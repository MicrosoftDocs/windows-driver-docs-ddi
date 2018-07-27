---
UID: NF:wudfddi.IWDFIoRequest.GetCreateParameters
title: IWDFIoRequest::GetCreateParameters
author: windows-driver-content
description: The GetCreateParameters method retrieves the request parameters for a create-type request.
old-location: wdf\iwdfiorequest_getcreateparameters.htm
tech.root: wdf
ms.assetid: 1bc6eed2-c6bd-448f-8f78-630cca4cd29a
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: GetCreateParameters, GetCreateParameters method, GetCreateParameters method,IWDFIoRequest interface, IWDFIoRequest interface,GetCreateParameters method, IWDFIoRequest.GetCreateParameters, IWDFIoRequest::GetCreateParameters, UMDFRequestObjectRef_ac352dd9-a9e0-4741-abfe-92482dd25112.xml, umdf.iwdfiorequest_getcreateparameters, wdf.iwdfiorequest_getcreateparameters, wudfddi/IWDFIoRequest::GetCreateParameters
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: wudfddi.h
req.include-header: Wudfddi.h
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
-	IWDFIoRequest.GetCreateParameters
product:
- Windows
targetos: Windows
req.typenames: 
---

# IWDFIoRequest::GetCreateParameters


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>GetCreateParameters</b> method retrieves the request parameters for a create-type request.


## -parameters




### -param pOptions [out, optional]

A pointer to a variable that receives a bitmask of flags that specify the options that are applied when creating or opening the file that is associated with the request and the action to be taken if the file already exists.

The high 8 bits of this parameter correspond to the <i>CreateDisposition</i> parameter of the kernel-mode <a href="https://msdn.microsoft.com/library/windows/hardware/ff566424">ZwCreateFile</a> function. These 8 bits specify the action to be taken, depending on whether the file already exists. Note that these disposition values differ from the values that are used in the <i>dwCreationDisposition</i> parameter of the Win32 <b>CreateFile</b> function.

The low 24 bits of this parameter correspond to the <i>CreateOptions</i> parameter of <a href="https://msdn.microsoft.com/library/windows/hardware/ff566424">ZwCreateFile</a>. 

This parameter is optional. The driver can pass <b>NULL</b> if the driver does not require the information. 


### -param pFileAttributes [out, optional]

A pointer to a variable that receives a bitmask of attribute flags that is applied when creating or opening the file that is associated with the request. Explicitly specified attributes are applied only when the file is created, superseded, or, in some situations, overwritten. By default, the single FILE_ATTRIBUTE_NORMAL flag is specified. However, this flag can be overridden by any other flag or by a bitwise OR combination of compatible flags. The bitmask of attribute flags corresponds to the <i>FileAttributes</i> parameter of <a href="https://msdn.microsoft.com/library/windows/hardware/ff566424">ZwCreateFile</a>.

This parameter is optional. The driver can pass <b>NULL</b> if the driver does not require the information. 


### -param pShareAccess [out, optional]

A pointer to a variable that receives a bitmask of flags that specify the share access rights that are requested for the file that is associated with the request. If the received bitmask is zero, exclusive access is being requested. For more information about share access, see the description of the <i>ShareAccess</i> parameter of <a href="https://msdn.microsoft.com/library/windows/hardware/ff566424">ZwCreateFile</a>.

This parameter is optional. The driver can pass <b>NULL</b> if the driver does not require the information. 


## -returns



None




## -remarks



Although the driver can optionally specify <b>NULL</b> for each of the <i>pOptions</i>, <i>pFileAttributes</i>, and <i>pShareAccess</i> parameters, the driver must specify at least one non-<b>NULL</b> parameter for <b>GetCreateParameters</b> to execute successfully.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff558985">IWDFIoRequest</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566424">ZwCreateFile</a>
 

 

