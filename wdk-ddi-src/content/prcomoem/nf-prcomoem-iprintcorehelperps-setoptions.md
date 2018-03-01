---
UID: NF:prcomoem.IPrintCoreHelperPS.SetOptions
title: IPrintCoreHelperPS::SetOptions method
author: windows-driver-content
description: The IPrintCoreHelperPS::SetOptions method sets multiple feature-option pairs at the same time.
old-location: print\iprintcorehelperps_setoptions.htm
old-project: print
ms.assetid: ba80f0f5-ecea-41d7-8ddd-58b417e1fbe7
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: IPrintCoreHelperPS, IPrintCoreHelperPS interface [Print Devices], SetOptions method, IPrintCoreHelperPS::SetOptions, SetOptions method [Print Devices], SetOptions method [Print Devices], IPrintCoreHelperPS interface, SetOptions,IPrintCoreHelperPS.SetOptions, prcomoem/IPrintCoreHelperPS::SetOptions, print.iprintcorehelperps_setoptions, print_unidrv-pscript_allplugins_7830001c-589d-4797-870c-cb48231745ed.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: prcomoem.h
req.include-header: Prcomoem.h
req.target-type: Desktop
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
req.lib: prcomoem.h
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	Prcomoem.h
api_name:
-	IPrintCoreHelperPS.SetOptions
product: Windows
targetos: Windows
req.typenames: OEMPTOPTS, *POEMPTOPTS
req.product: Windows 10 or later.
---

# IPrintCoreHelperPS::SetOptions method


## -description


The <b>IPrintCoreHelperPS::SetOptions</b> method sets multiple feature-option pairs at the same time.


## -syntax


````
STDMETHOD  SetOptions(
  [in, optional] PDEVMODE                   pDevmode,
  [in]           DWORD                      cbSize,
  [in]           BOOL                       bResolveConflicts,
  [in]           CONST PRINT_FEATURE_OPTION pFOPairs[],
  [in]           DWORD                      cPairs,
  [out]          PDWORD                     pcPairsWritten,
  [out]          PDWORD                     pdwResult
);
````


## -parameters




### -param pDevmode [in, optional]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff552837">DEVMODEW</a> structure. If this pointer is provided, <b>IPrintCoreHelperPS::SetOptions</b> should use the DEVMODEW structure that is pointed to by <i>pDevmode</i> rather than the default or current DEVMODEW structure. If this method is called from the plug-in provider or from <a href="https://msdn.microsoft.com/library/windows/hardware/ff553205">IPrintOemPS::DevMode</a>, this parameter is required. In most other situations, the parameter should be <b>NULL</b>. When the core driver sets <i>pDevmode</i> to <b>NULL</b>, it modifies its internal state rather than that of the passed-in DEVMODEW structure. This is required during operations such as full UI replacement, where the DEVMODEW structure returned by a DDI, such as <a href="..\winddiui\nf-winddiui-drvdocumentpropertysheets.md">DrvDocumentPropertySheets</a>, is being serviced by the core driver's UI module.


### -param cbSize [in]

The size, in bytes, of the DEVMODEW structure that is pointed to by the <i>pDevmode</i> parameter. 


### -param bResolveConflicts [in]

A Boolean value that indicates whether <b>IPrintCoreHelperPS::SetOptions</b> should resolve conflicts that arise from one or more constraints in the PPD view of the configuration file, as well as constraints for functionality that are implemented by Pscript or the print processor. If <b>TRUE</b>, this method should attempt to resolve the conflict. If <b>FALSE</b>, this method should not attempt to resolve conflicts.


### -param pFOPairs




### -param cPairs [in]

The number of feature-option pairs that are pointed to by the <i>pFOPairs</i> parameter. 


### -param pcPairsWritten [out]

A pointer to a variable that receives the number of feature-option pairs that were successfully saved before <b>IPrintCoreHelperPS::SetOptions</b> returned or failed. If this method returns successfully, *<i>pcPairsWritten</i> will have the same value as <i>cPairs</i>. If the method fails, *<i>pcPairsWritten</i> can have any value from zero through the value of <i>cPairs</i>. This parameter is optional and can be <b>NULL</b>.


### -param pdwResult [out]

A pointer to a variable that receives the status of the conflict resolution. The status can be one of the following values.

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
SETOPTIONS_RESULT_NO_CONFLICT

</td>
<td>
No constraint that was specified in the PPD view of the configuration file was violated, relative to the new setting.

</td>
</tr>
<tr>
<td>
SETOPTIONS_RESULT_CONFLICT_RESOLVED

</td>
<td>
At least one constraint that was specified in the PPD view of the configuration file was violated, and the caller requested that the method should resolve conflicts. This value results in changed settings with conflicts resolved.

</td>
</tr>
<tr>
<td>
SETOPTIONS_RESULT_CONFLICT_NOT_RESOLVED

</td>
<td>
At least one constraint that was specified in the PPD view of the configuration file was violated, and the caller requested that the method should not resolve conflicts. The settings do not change, and conflicts remain.

</td>
</tr>
</table>
 


#### - pFOPairs[] [in]

An array of <a href="..\prcomoem\ns-prcomoem-_print_feature_option.md">PRINT_FEATURE_OPTION</a> elements, where each element contains a feature-option pair. Each feature-option pair lists a feature and the option to select for that feature. All settings are applied sequentially. Duplicates are not disallowed, but settings that appear later in the array (that is, at a higher index) override those that appear earlier in the array. 


## -returns



<b>IPrintCoreHelperPS::SetOptions</b> should return one of the following values.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>S_OK</b></dt>
</dl>
</td>
<td width="60%">
The operation succeeded.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_INVALIDARG</b></dt>
</dl>
</td>
<td width="60%">
One or more of the arguments is invalid, or the feature was not supported.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_OUTOFMEMORY</b></dt>
</dl>
</td>
<td width="60%">
Memory for the result array could not be allocated.

</td>
</tr>
</table>
 

For other failures, the method should return a standard COM error code.




## -remarks



<b>IPrintCoreHelperPS::SetOptions</b> can be used to make multiple settings changes simultaneously and to resolve constraints after all of the selected options have been set. Changes to options are applied sequentially, starting from the beginning of the <i>pFOPairs</i> array, so if the same feature appears twice in this array, only the last option for the feature will be selected. Changes to options are not committed unless the <i>bResolveConflicts</i> parameter is <b>TRUE</b>.

For most scenarios the <i>bResolveConflicts</i> parameter should be set to <b>TRUE</b>. Set this parameter to <b>FALSE</b> if you want to prompt the user to resolve conflicts.




## -see-also

<a href="https://msdn.microsoft.com/fa212b86-89ae-4d22-a3ff-ebcc6100874b">IPrintCoreHelperPS::GetOptions</a>



<a href="..\prcomoem\nn-prcomoem-iprintcorehelperps.md">IPrintCoreHelperPS</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20IPrintCoreHelperPS::SetOptions method%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

