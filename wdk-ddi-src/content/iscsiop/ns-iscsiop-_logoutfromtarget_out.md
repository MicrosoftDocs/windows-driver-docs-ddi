---
UID: NS:iscsiop._LogoutFromTarget_OUT
title: "_LogoutFromTarget_OUT"
author: windows-driver-content
description: The LogoutFromTarget_OUT structure holds the output data for the LogoutFromTarget method.
old-location: storage\logoutfromtarget_out.htm
old-project: storage
ms.assetid: 15231188-5c6d-4e36-afe9-74b92f445fa3
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PLogoutFromTarget_OUT, LogoutFromTarget_OUT, LogoutFromTarget_OUT structure [Storage Devices], PLogoutFromTarget_OUT, PLogoutFromTarget_OUT structure pointer [Storage Devices], _LogoutFromTarget_OUT, iscsiop/LogoutFromTarget_OUT, iscsiop/PLogoutFromTarget_OUT, storage.logoutfromtarget_out, structs-iSCSI_3ef612e0-305e-4015-8b77-5c2577e2b6aa.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: iscsiop.h
req.include-header: Iscsiop.h
req.target-type: Windows
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	iscsiop.h
api_name:
-	LogoutFromTarget_OUT
product: Windows
targetos: Windows
req.typenames: LogoutFromTarget_OUT, *PLogoutFromTarget_OUT
---

# _LogoutFromTarget_OUT structure


## -description


The LogoutFromTarget_OUT structure holds the output data for the <a href="https://msdn.microsoft.com/library/windows/hardware/ff561602">LogoutFromTarget</a> method.


## -syntax


````
typedef struct _LogoutFromTarget_OUT {
  ULONG Status;
} LogoutFromTarget_OUT, *PLogoutFromTarget_OUT;
````


## -struct-fields




### -field Status

On output from <b>LogoutFromTarget</b>, the status of the logoff operation. For a list of status qualifiers, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff561568">ISCSI_STATUS_QUALIFIERS</a>.


## -remarks



You must implement this method.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff561602">LogoutFromTarget</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563091">MSiSCSI_Operations WMI Class</a>



<a href="..\iscsiop\ns-iscsiop-_logoutfromtarget_in.md">LogoutFromTarget_IN</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561599">LoginToTarget</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561568">ISCSI_STATUS_QUALIFIERS</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20LogoutFromTarget_OUT structure%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

