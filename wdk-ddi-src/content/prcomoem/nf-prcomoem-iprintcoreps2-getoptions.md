---
UID: NF:prcomoem.IPrintCorePS2.GetOptions
title: IPrintCorePS2::GetOptions method
author: windows-driver-content
description: The IPrintCorePS2::GetOptions method retrieves the driver's current feature settings in the format of a list of feature/option keyword pairs.
old-location: print\iprintcoreps2_getoptions.htm
old-project: print
ms.assetid: 8f5df76b-57c9-4c5a-9ca2-f02c8d903a8b
ms.author: windowsdriverdev
ms.date: 1/8/2018
ms.keywords: IPrintCorePS2, IPrintCorePS2::GetOptions, GetOptions
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
req.alt-api: IPrintCorePS2.GetOptions
req.alt-loc: prcomoem.h
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
req.typenames: OEMPTOPTS, *POEMPTOPTS
req.product: Windows 10 or later.
---

# IPrintCorePS2::GetOptions method



## -description
The <code>IPrintCorePS2::GetOptions</code> method retrieves the driver's current feature settings in the format of a list of feature/option keyword pairs.



## -syntax

````
HRESULT GetOptions(
  [in]  PDEVOBJ pdevobj,
  [in]  DWORD   dwFlags,
  [in]  PCSTR   pmszFeaturesRequested,
  [in]  DWORD   cbIn,
  [out] PSTR    pmszFeatureOptionBuf,
  [in]  DWORD   cbSize,
  [out] PDWORD  pcbNeeded
);
````


## -parameters

### -param pdevobj [in]

Pointer to a <a href="..\printoem\ns-printoem-_devobj.md">DEVOBJ</a> structure.


### -param dwFlags [in]

Is reserved and must be set to zero.


### -param pmszFeaturesRequested [in]

Pointer to caller-supplied buffer containing a list of feature keywords (in MULTI_SZ format) whose settings are requested. Set this parameter to <b>NULL</b> to obtain settings for all features.


### -param cbIn [in]

Specifies the size, in bytes, of the buffer pointed to by <i>pmszFeaturesRequested</i>. The size includes the last MULTI_SZ null character.


### -param pmszFeatureOptionBuf [out]

Pointer to a caller-supplied buffer that receives a list of feature/option keyword pairs (in MULTI_SZ format) obtained from the driver settings. Each feature/option keyword pair contains the feature keyword name, a null character, the option keyword name, and another null character. The list is terminated by two NULL characters.


### -param cbSize [in]

Specifies the size, in bytes, of the buffer pointed to by <i>pmszFeatureOptionBuf</i>.


### -param pcbNeeded [out]

Pointer to a memory location that receives the actual size, in bytes, of the requested data.


## -returns
The method must return one of the following values.
<dl>
<dt><b>S_OK</b></dt>
</dl>The method succeeded.
<dl>
<dt><b>E_OUTOFMEMORY</b></dt>
</dl>The value in <i>cbSize</i> was smaller than the number of bytes to be written to the output buffer (the buffer pointed to by <i>pmszFeatureOptionBuf</i>).

The method was called with <i>pmszFeatureOptionBuf</i> set to <b>NULL</b>.
<dl>
<dt><b>E_INVALIDARG</b></dt>
</dl>The input buffer (the buffer pointed to by <i>pmszFeaturesRequested</i>) was provided, but its contents were not in MULTI_SZ format.

The <i>pdevobj</i> parameter pointed to an invalid driver context object.
<dl>
<dt><b>E_NOTIMPL</b></dt>
</dl>The method is not supported.
<dl>
<dt><b>E_FAIL</b></dt>
</dl>The method failed.

 


## -remarks
This method supports both <a href="wdkgloss.d#wdkgloss.document-sticky#wdkgloss.document-sticky"><i>document-sticky</i></a> and <a href="wdkgloss.p#wdkgloss.printer-sticky#wdkgloss.printer-sticky"><i>printer-sticky</i></a> features. It is supported only after the core driver finishes its <a href="https://msdn.microsoft.com/library/windows/hardware/ff556211">DrvEnablePDEV</a> processing, which sets up all option settings. A call to <code>IPrintCorePS2::GetOptions</code> when it is not supported should cause it to return E_NOTIMPL. For example, when the core driver calls a render plug-in's <a href="https://msdn.microsoft.com/library/windows/hardware/ff553215">IPrintOemPS::EnablePDEV</a> method, the driver is still occupied with its <b>DrvEnablePDEV</b> processing, so if the plug-in calls <code>IPrintCorePS2::GetOptions</code> within the plug-in's <b>IPrintOemPS::DevMode</b> method, the plug-in receives the E_NOTIMPL return value. However, because the plug-in's <b>IPrintOemPS::EnablePDEV</b> method is called after the core driver finishes its <b>DrvEnablePDEV</b> processing, the plug-in is able to call <code>IPrintCorePS2::GetOptions</code> successfully within its <b>IPrintOemPS::EnablePDEV</b> method.

If a requested feature keyword is not recognized, or the feature is recognized but there is currently no option selection for it, the feature is ignored and the feature/option keyword pair is not placed in the output buffer.

To reduce the need to make two calls per data access, pass the method an output buffer of a fixed size (1 KB, for example), and then check the function return value. If the method returns S_OK, the buffer already contains the data of interest. If the method returns E_OUTOFMEMORY, the value in *<i>pcbNeeded</i> is the buffer size needed to hold the data of interest. The caller should then allocate a buffer of that larger size and proceed with a second call to the method.

This method is supported for any Pscript5 render plug-in.

For more information, see <a href="https://msdn.microsoft.com/c8b5c235-0b74-47c8-b6ba-eba810a8467b">Using GetOptions and SetOptions</a>.


## -see-also
<dl>
<dt>
<a href="..\printoem\ns-printoem-_devobj.md">DEVOBJ</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff556211">DrvEnablePDEV</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff553205">IPrintOemPS::DevMode</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff553215">IPrintOemPS::EnablePDEV</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20IPrintCorePS2::GetOptions method%20 RELEASE:%20(1/8/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

