---
UID: NS:ntifs._WIM_PROVIDER_EXTERNAL_INFO
title: "_WIM_PROVIDER_EXTERNAL_INFO"
author: windows-driver-content
description: The WIM_PROVIDER_EXTERNAL_INFO structure holds the identifier and status information for the Windows Image File (WIM) external backing provider.
old-location: ifsk\wim_provider_external_info.htm
old-project: ifsk
ms.assetid: CD51FBD6-A589-4135-8BF0-8F0075654A05
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: "*PWIM_PROVIDER_EXTERNAL_INFO, PWIM_PROVIDER_EXTERNAL_INFO, PWIM_PROVIDER_EXTERNAL_INFO structure pointer [Installable File System Drivers], WIM_PROVIDER_EXTERNAL_FLAG_NOT_ACTIVE, WIM_PROVIDER_EXTERNAL_FLAG_SUSPENDED, WIM_PROVIDER_EXTERNAL_INFO, WIM_PROVIDER_EXTERNAL_INFO structure [Installable File System Drivers], _WIM_PROVIDER_EXTERNAL_INFO, ifsk.wim_provider_external_info, ntifs/PWIM_PROVIDER_EXTERNAL_INFO, ntifs/WIM_PROVIDER_EXTERNAL_INFO"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntifs.h
req.include-header: Ntifs.h, Fltkernel.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with Windows 8.1 Update.
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ntifs.h
api_name:
-	WIM_PROVIDER_EXTERNAL_INFO
product: Windows
targetos: Windows
req.typenames: WIM_PROVIDER_EXTERNAL_INFO, *PWIM_PROVIDER_EXTERNAL_INFO
---

# _WIM_PROVIDER_EXTERNAL_INFO structure


## -description


The <b>WIM_PROVIDER_EXTERNAL_INFO</b> structure holds the identifier and status information for the Windows Image File (WIM) external backing provider. 


## -struct-fields




### -field Version

The WIM provider version. Set to WIM_PROVIDER_CURRENT_VERSION.


### -field Flags

The status flags for the WIM provider. Set to 0 when active. Otherwise <b>Flags</b> is set to one of the following values.

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%"><a id="WIM_PROVIDER_EXTERNAL_FLAG_NOT_ACTIVE"></a><a id="wim_provider_external_flag_not_active"></a><dl>
<dt><b>WIM_PROVIDER_EXTERNAL_FLAG_NOT_ACTIVE</b></dt>
</dl>
</td>
<td width="60%">
The WIM provider is not active. This can occur when the WIM file is  not found. In this case the WIM file will not be recovered.

</td>
</tr>
<tr>
<td width="40%"><a id="WIM_PROVIDER_EXTERNAL_FLAG_SUSPENDED"></a><a id="wim_provider_external_flag_suspended"></a><dl>
<dt><b>WIM_PROVIDER_EXTERNAL_FLAG_SUSPENDED</b></dt>
</dl>
</td>
<td width="60%">
Indicates that the provider is dismounted. Recovery will be attempted.

</td>
</tr>
</table>
 


### -field DataSourceId

An identifier value for the WIM file data source.


### -field ResourceHash

An identifier for the object contained within the WIM.  Conventionally a hash of the contents of a file, stored within the WIM.


## -remarks



The backing source for a file is set with a <a href="https://msdn.microsoft.com/library/windows/hardware/dn632443">FSCTL_SET_EXTERNAL_BACKING</a> control code request. The WIM file backing the file specified in the request is set in the <b>DataSourceId</b> member of <b>WIM_PROVIDER_EXTERNAL_INFO</b>.

The <b>Flags</b> and <b>ResourceHash</b> members are valid when the provider info is returned from a <a href="https://msdn.microsoft.com/library/windows/hardware/dn632441">FSCTL_GET_EXTERNAL_BACKING</a> request.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/dn632441">FSCTL_GET_EXTERNAL_BACKING</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn632443">FSCTL_SET_EXTERNAL_BACKING</a>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20WIM_PROVIDER_EXTERNAL_INFO structure%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

