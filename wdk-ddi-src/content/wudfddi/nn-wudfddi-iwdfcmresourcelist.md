---
UID: NN:wudfddi.IWDFCmResourceList
title: IWDFCmResourceList
author: windows-driver-content
description: This interface represents a list of hardware resources for a device.
old-location: wdf\iwdfcmresourcelist.htm
old-project: wdf
ms.assetid: 8C03A1A3-1757-4622-9652-0D84DC0AFE59
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: wdf.iwdfcmresourcelist, IWDFCmResourceList interface, IWDFCmResourceList interface, described, IWDFCmResourceList, wudfddi/IWDFCmResourceList, umdf.iwdfcmresourcelist
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: interface
req.header: wudfddi.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 1.11
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
-	IWDFCmResourceList
product: Windows
targetos: Windows
req.typenames: "*PPOWER_ACTION, POWER_ACTION"
req.product: Windows 10 or later.
---

# IWDFCmResourceList interface


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

This interface represents a list of hardware resources for a device.


## -members

The <b>IWDFCmResourceList</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff597609">GetCount</a>
</td>
<td align="left" width="63%">
Returns the number of resource descriptors that are contained in a specified resource list.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/hh439771">GetDescriptor</a>
</td>
<td align="left" width="63%">
Returns a pointer to a resource descriptor that is contained in a specified resource list.

</td>
</tr>
</table>Returns the number of resource descriptors that are contained in a specified resource list.

Returns a pointer to a resource descriptor that is contained in a specified resource list.

 


## -remarks



After a UMDF driver receives a translated resource list in its <a href="https://msdn.microsoft.com/library/windows/hardware/hh439734">OnPrepareHardware</a> callback, it can use <b>IWDFCmResourceList</b> to scan through the list and identify its port and register resources. 




## -see-also

<a href="https://msdn.microsoft.com/2361CEA9-A58C-4019-B4F6-BA1D7DEE3A80">Framework Resource-List Object Methods</a>



<a href="..\wudfddi\nn-wudfddi-iwdfobject.md">IWDFObject</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20IWDFCmResourceList interface%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

