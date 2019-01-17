---
UID: NF:wdm.CmCallbackGetKeyObjectID
title: CmCallbackGetKeyObjectID function
description: The CmCallbackGetKeyObjectID routine retrieves the unique identifier and object name that are associated with a specified registry key object.
old-location: kernel\cmcallbackgetkeyobjectid.htm
tech.root: kernel
ms.assetid: e8db3009-7941-4fcc-a888-22c887bf59d5
ms.date: 04/30/2018
ms.keywords: CmCallbackGetKeyObjectID, CmCallbackGetKeyObjectID routine [Kernel-Mode Driver Architecture], ConfigMgrRef_dbab8a69-78b4-4ae8-8409-e62e62ea8b9e.xml, kernel.cmcallbackgetkeyobjectid, wdm/CmCallbackGetKeyObjectID
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows Vista.
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
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: "<= APC_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	CmCallbackGetKeyObjectID
product:
- Windows
targetos: Windows
req.typenames: 
---

# CmCallbackGetKeyObjectID function


## -description


The <b>CmCallbackGetKeyObjectID</b> routine retrieves the unique identifier and object name that are associated with a specified registry key object.
<div class="alert"><b>Note</b>  Starting with Windows 8, registry filter drivers should call the <a href="https://msdn.microsoft.com/library/windows/hardware/jj215789">CmCallbackGetKeyObjectIDEx</a> routine instead of <b>CmCallbackGetKeyObjectID</b>. For more information, see Remarks.</div><div> </div>

## -parameters




### -param Cookie [in]

The cookie value that the driver previously obtained by calling the <a href="https://msdn.microsoft.com/library/windows/hardware/ff541918">CmRegisterCallback</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff541921">CmRegisterCallbackEx</a> routine.


### -param Object [in]

The pointer value that the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff560903">RegistryCallback</a> callback routine received in the <b>Object</b> member of one of the <b>REG_<i>XXX</i>_KEY_INFORMATION</b> structures. 

<div class="alert"><b>Warning</b>  In certain circumstances registry callback notification structures may contain invalid non-NULL object pointers. Registry filtering drivers must not pass such pointers to this routine. For more information, see <a href="https://go.microsoft.com/fwlink/p/?linkid=613134">Invalid Key Object Pointers in Registry Notifications</a>.</div>
<div> </div>

### -param ObjectID [out, optional]

A pointer to a location that receives a pointer to the unique identifier that represents the registry key that <i>Object</i> specifies. This parameter is optional and can be <b>NULL</b>.


### -param ObjectName [out, optional]

A pointer to a location that receives a pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff564879">UNICODE_STRING</a> structure. This structure contains the object name of the registry key object that <i>Object</i> specifies. The object name is actually the full path name of the registry key that the object represents. The caller must not write to this <b>UNICODE_STRING</b> structure or free it. This parameter is optional and can be <b>NULL</b>.


## -returns



<b>CmCallbackGetKeyObjectID</b> returns STATUS_SUCCESS if the operation succeeds. Possible error return values include the following status code.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
The <i>Cookie</i> or <i>Object</i> parameter is invalid.

</td>
</tr>
</table>
 




## -remarks



The <b>CmCallbackGetKeyObjectID</b> routine is available starting with Windows Vista. An improved version of this routine, <a href="https://msdn.microsoft.com/library/windows/hardware/jj215789">CmCallbackGetKeyObjectIDEx</a>, is available starting with Windows 8. Drivers that run only in Windows 8 and later versions of Windows should call <b>CmCallbackGetKeyObjectIDEx</b> instead of <b>CmCallbackGetKeyObjectID</b>.

Drivers can use <b>CmCallbackGetKeyObjectID</b> to obtain the registry key identifier, the object name, or both, by supplying non-<b>NULL</b> values for the <i>ObjectID</i> or <i>ObjectName</i> parameters.

After the driver has obtained the identifier or name, the identifier or name is valid until the driver's <i>RegistryCallback</i> routine receives pre-notification of handle closure.

The driver must not modify the object name.

If two registry key objects represent the same registry key, the key identifiers for both objects are identical.

For more information about <b>CmCallbackGetKeyObjectID</b> and registry filtering operations, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff545879">Filtering Registry Calls</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/jj215789">CmCallbackGetKeyObjectIDEx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541918">CmRegisterCallback</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541921">CmRegisterCallbackEx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff560903">RegistryCallback</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564879">UNICODE_STRING</a>
 

 

