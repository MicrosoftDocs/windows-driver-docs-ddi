---
UID: NF:wudfddi.IWDFIoRequest.GetCreateParameters
title: IWDFIoRequest::GetCreateParameters method
author: windows-driver-content
description: The GetCreateParameters method retrieves the request parameters for a create-type request.
old-location: wdf\iwdfiorequest_getcreateparameters.htm
old-project: wdf
ms.assetid: 1bc6eed2-c6bd-448f-8f78-630cca4cd29a
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: IWDFIoRequest interface, GetCreateParameters method, wdf.iwdfiorequest_getcreateparameters, IWDFIoRequest, umdf.iwdfiorequest_getcreateparameters, GetCreateParameters method, GetCreateParameters method, IWDFIoRequest interface, IWDFIoRequest::GetCreateParameters, wudfddi/IWDFIoRequest::GetCreateParameters, UMDFRequestObjectRef_ac352dd9-a9e0-4741-abfe-92482dd25112.xml, GetCreateParameters
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
req.lib: wudfddi.h
req.dll: WUDFx.dll
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	WUDFx.dll
apiname:
-	IWDFIoRequest.GetCreateParameters
product: Windows
targetos: Windows
req.typenames: "*PPOWER_ACTION, POWER_ACTION"
req.product: Windows 10 or later.
---

# IWDFIoRequest::GetCreateParameters method


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>GetCreateParameters</b> method retrieves the request parameters for a create-type request.


## -syntax


````
void GetCreateParameters(
  [out, optional] ULONG  *pOptions,
  [out, optional] USHORT *pFileAttributes,
  [out, optional] USHORT *pShareAccess
);
````


## -parameters




### -param pOptions [out, optional]

A pointer to a variable that receives a bitmask of flags that specify the options that are applied when creating or opening the file that is associated with the request and the action to be taken if the file already exists.

The high 8 bits of this parameter correspond to the <i>CreateDisposition</i> parameter of the kernel-mode <a href="..\wdm\nf-wdm-zwcreatefile.md">ZwCreateFile</a> function. These 8 bits specify the action to be taken, depending on whether the file already exists. Note that these disposition values differ from the values that are used in the <i>dwCreationDisposition</i> parameter of the Win32 <b>CreateFile</b> function.

The low 24 bits of this parameter correspond to the <i>CreateOptions</i> parameter of <a href="..\wdm\nf-wdm-zwcreatefile.md">ZwCreateFile</a>. 

This parameter is optional. The driver can pass <b>NULL</b> if the driver does not require the information. 


### -param pFileAttributes [out, optional]

A pointer to a variable that receives a bitmask of attribute flags that is applied when creating or opening the file that is associated with the request. Explicitly specified attributes are applied only when the file is created, superseded, or, in some situations, overwritten. By default, the single FILE_ATTRIBUTE_NORMAL flag is specified. However, this flag can be overridden by any other flag or by a bitwise OR combination of compatible flags. The bitmask of attribute flags corresponds to the <i>FileAttributes</i> parameter of <a href="..\wdm\nf-wdm-zwcreatefile.md">ZwCreateFile</a>.

This parameter is optional. The driver can pass <b>NULL</b> if the driver does not require the information. 


### -param pShareAccess [out, optional]

A pointer to a variable that receives a bitmask of flags that specify the share access rights that are requested for the file that is associated with the request. If the received bitmask is zero, exclusive access is being requested. For more information about share access, see the description of the <i>ShareAccess</i> parameter of <a href="..\wdm\nf-wdm-zwcreatefile.md">ZwCreateFile</a>.

This parameter is optional. The driver can pass <b>NULL</b> if the driver does not require the information. 


## -returns


None



## -remarks


Although the driver can optionally specify <b>NULL</b> for each of the <i>pOptions</i>, <i>pFileAttributes</i>, and <i>pShareAccess</i> parameters, the driver must specify at least one non-<b>NULL</b> parameter for <b>GetCreateParameters</b> to execute successfully.



## -see-also

<a href="..\wdm\nf-wdm-zwcreatefile.md">ZwCreateFile</a>

<a href="..\wudfddi\nn-wudfddi-iwdfiorequest.md">IWDFIoRequest</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20IWDFIoRequest::GetCreateParameters method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

