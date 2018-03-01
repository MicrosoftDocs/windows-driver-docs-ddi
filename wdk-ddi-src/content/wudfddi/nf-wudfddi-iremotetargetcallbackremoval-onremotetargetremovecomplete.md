---
UID: NF:wudfddi.IRemoteTargetCallbackRemoval.OnRemoteTargetRemoveComplete
title: IRemoteTargetCallbackRemoval::OnRemoteTargetRemoveComplete method
author: windows-driver-content
description: A UMDF-based driver's OnRemoteTargetRemoveComplete event callback function performs operations that are necessary after the operating system completes the removal of a remote I/O target's device.
old-location: wdf\iremotetargetcallbackremoval_onremotetargetremovecomplete.htm
old-project: wdf
ms.assetid: bfac8f91-2367-4194-8e98-e274025c049a
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: IRemoteTargetCallbackRemoval, IRemoteTargetCallbackRemoval interface, OnRemoteTargetRemoveComplete method, IRemoteTargetCallbackRemoval::OnRemoteTargetRemoveComplete, OnRemoteTargetRemoveComplete method, OnRemoteTargetRemoveComplete method, IRemoteTargetCallbackRemoval interface, OnRemoteTargetRemoveComplete,IRemoteTargetCallbackRemoval.OnRemoteTargetRemoveComplete, UMDFIoTargetObjectRef_bec0246d-a3e9-41b2-b577-fef78c8e4668.xml, umdf.iremotetargetcallbackremoval_onremotetargetremovecomplete, wdf.iremotetargetcallbackremoval_onremotetargetremovecomplete, wudfddi/IRemoteTargetCallbackRemoval::OnRemoteTargetRemoveComplete
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: wudfddi.h
req.include-header: Wudfddi.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 1.9
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: Unavailable in UMDF 2.0 and later.
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: wudfddi.h
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	Wudfddi.h
api_name:
-	IRemoteTargetCallbackRemoval.OnRemoteTargetRemoveComplete
product: Windows
targetos: Windows
req.typenames: POWER_ACTION, *PPOWER_ACTION
req.product: Windows 10 or later.
---

# IRemoteTargetCallbackRemoval::OnRemoteTargetRemoveComplete method


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

A UMDF-based driver's <b>OnRemoteTargetRemoveComplete</b> event callback function performs operations that are necessary after the operating system completes the removal of a remote I/O target's device.


## -syntax


````
void OnRemoteTargetRemoveComplete(
  [in] IWDFRemoteTarget *pWdfRemoteTarget
);
````


## -parameters




### -param pWdfRemoteTarget [in]

A pointer to the <a href="..\wudfddi\nn-wudfddi-iwdfremotetarget.md">IWDFRemoteTarget</a> interface of a remote target object that represents a <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/general-i-o-targets-in-umdf">remote I/O target</a>. The driver obtains this pointer when it calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff556928">IWDFDevice2::CreateRemoteTarget</a>.


## -returns



None.




## -remarks



If your driver provides an <b>OnRemoteTargetRemoveComplete</b> event callback function, the callback function should do the following:

<ol>
<li>
Do any driver-specific actions that your driver requires to close the remote I/O target.

</li>
<li>
Call <a href="https://msdn.microsoft.com/library/windows/hardware/ff560253">IWDFRemoteTarget::Close</a>.

</li>
</ol>
If the driver does not provide this callback function, the framework calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff560253">IWDFRemoteTarget::Close</a> for the driver.

For more information about the <b>OnRemoteTargetRemoveComplete</b> event callback function, see <a href="https://msdn.microsoft.com/479487b2-5ce5-4522-b195-58ee50d210b6">Controlling a General I/O Target's State in UMDF</a>.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff556899">IRemoteTargetCallbackRemoval::OnRemoteTargetRemoveCanceled</a>



<a href="..\wudfddi\nn-wudfddi-iremotetargetcallbackremoval.md">IRemoteTargetCallbackRemoval</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556897">IRemoteTargetCallbackRemoval::OnRemoteTargetQueryRemove</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20IRemoteTargetCallbackRemoval::OnRemoteTargetRemoveComplete method%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

