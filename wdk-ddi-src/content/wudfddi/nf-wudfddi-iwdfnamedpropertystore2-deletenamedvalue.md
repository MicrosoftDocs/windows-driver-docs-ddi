---
UID: NF:wudfddi.IWDFNamedPropertyStore2.DeleteNamedValue
title: IWDFNamedPropertyStore2::DeleteNamedValue method
author: windows-driver-content
description: The DeleteNamedValue method deletes a value name from the registry.
old-location: wdf\iwdfnamedpropertystore2_deletenamedvalue.htm
old-project: wdf
ms.assetid: ce0953d3-054f-446b-9f69-58f4580740f3
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DeleteNamedValue method, DeleteNamedValue method, IWDFNamedPropertyStore2 interface, DeleteNamedValue,IWDFNamedPropertyStore2.DeleteNamedValue, IWDFNamedPropertyStore2, IWDFNamedPropertyStore2 interface, DeleteNamedValue method, IWDFNamedPropertyStore2::DeleteNamedValue, UMDFPropertyStoreObjectRef_9363c14f-0ff0-4c2f-910a-916b3cb9d664.xml, umdf.iwdfnamedpropertystore2_deletenamedvalue, wdf.iwdfnamedpropertystore2_deletenamedvalue, wudfddi/IWDFNamedPropertyStore2::DeleteNamedValue
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
-	IWDFNamedPropertyStore2.DeleteNamedValue
product:
- Windows
targetos: Windows
req.typenames: POWER_ACTION, *PPOWER_ACTION
req.product: Windows 10 or later.
---

# IWDFNamedPropertyStore2::DeleteNamedValue method


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>DeleteNamedValue</b> method deletes a value name from the registry.


## -parameters




### -param pwszName [in]

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



Before a driver calls <b>DeleteNamedValue</b>, it must call <a href="https://msdn.microsoft.com/library/windows/hardware/ff560228">IWDFPropertyStoreFactory::RetrieveDevicePropertyStore</a> to obtain the <a href="https://msdn.microsoft.com/library/windows/hardware/ff560168">IWDFNamedPropertyStore2</a> interface.

For more information about accessing the registry, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/using-the-registry-in-umdf-1-x-drivers">Using the Registry in UMDF-based Drivers</a>.


#### Examples

The following code example is an <a href="https://msdn.microsoft.com/library/windows/hardware/ff556760">IObjectCleanup::OnCleanup</a> callback function for a device object. If the driver had previously added a value to the registry's <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/using-the-registry-in-umdf-1-x-drivers">DEVICEMAP key</a>, the callback function deletes the value.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>VOID 
CMyDevice::OnCleanup(
 IWDFObject*  pWdfObject
)
{
    UNREFERENCED_PARAMETER(pWdfObject);
 
    if ((m_CreatedLegacyHardwareKey == TRUE) &amp;&amp; 
        (m_LegacyHardwarePropertyStore != NULL))
    {
        m_LegacyHardwarePropertyStore-&gt;DeleteNamedValue(m_PdoName);
        SAFE_RELEASE(m_LegacyHardwarePropertyStore);
        delete[] m_PdoName;
    }    
}</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff560168">IWDFNamedPropertyStore2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff560228">IWDFPropertyStoreFactory::RetrieveDevicePropertyStore</a>
 

 

