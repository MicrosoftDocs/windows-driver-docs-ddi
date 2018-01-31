---
UID: NF:wudfddi.IWDFNamedPropertyStore2.DeleteNamedValue
title: IWDFNamedPropertyStore2::DeleteNamedValue method
author: windows-driver-content
description: The DeleteNamedValue method deletes a value name from the registry.
old-location: wdf\iwdfnamedpropertystore2_deletenamedvalue.htm
old-project: wdf
ms.assetid: ce0953d3-054f-446b-9f69-58f4580740f3
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: UMDFPropertyStoreObjectRef_9363c14f-0ff0-4c2f-910a-916b3cb9d664.xml, IWDFNamedPropertyStore2, IWDFNamedPropertyStore2 interface, DeleteNamedValue method, DeleteNamedValue method, DeleteNamedValue, DeleteNamedValue method, IWDFNamedPropertyStore2 interface, wdf.iwdfnamedpropertystore2_deletenamedvalue, umdf.iwdfnamedpropertystore2_deletenamedvalue, IWDFNamedPropertyStore2::DeleteNamedValue, wudfddi/IWDFNamedPropertyStore2::DeleteNamedValue
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
-	IWDFNamedPropertyStore2.DeleteNamedValue
product: Windows
targetos: Windows
req.typenames: POWER_ACTION, *PPOWER_ACTION
req.product: Windows 10 or later.
---

# IWDFNamedPropertyStore2::DeleteNamedValue method


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>DeleteNamedValue</b> method deletes a value name from the registry.


## -syntax


````
HRESULT DeleteNamedValue(
  [in] LPCWSTR pwszName
);
````


## -parameters




#### - pwszName [in]

A pointer to a <b>null</b>-terminated string that contains a registry value name.


## -returns


<b>DeleteNamedValue</b> returns S_OK if the operation succeeds. Otherwise, the method might return the following value:
<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_INVALIDARG</b></dt>
</dl>
</td>
<td width="60%">
The caller provided an invalid input argument.

</td>
</tr>
</table> 

This method might return one of the other values that Winerror.h contains.



## -remarks


Before a driver calls <b>DeleteNamedValue</b>, it must call <a href="https://msdn.microsoft.com/library/windows/hardware/ff560228">IWDFPropertyStoreFactory::RetrieveDevicePropertyStore</a> to obtain the <a href="..\wudfddi\nn-wudfddi-iwdfnamedpropertystore2.md">IWDFNamedPropertyStore2</a> interface.

For more information about accessing the registry, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/using-the-registry-in-umdf-1-x-drivers">Using the Registry in UMDF-based Drivers</a>.



## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff560228">IWDFPropertyStoreFactory::RetrieveDevicePropertyStore</a>

<a href="..\wudfddi\nn-wudfddi-iwdfnamedpropertystore2.md">IWDFNamedPropertyStore2</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20IWDFNamedPropertyStore2::DeleteNamedValue method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

