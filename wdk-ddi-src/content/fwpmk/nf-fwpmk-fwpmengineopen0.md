---
UID: NF:fwpmk.FwpmEngineOpen0
title: FwpmEngineOpen0 function
author: windows-driver-content
description: The FwpmEngineOpen0 function opens a session to the filter engine.Note  FwpmEngineOpen0 is a specific version of FwpmEngineOpen.
old-location: netvista\fwpmengineopen0.htm
old-project: netvista
ms.assetid: 4d805ffe-7cf9-4cbc-9077-e191ddc24ecd
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ",  , 0, E, F, FwpmEngineOpen0, FwpmEngineOpen0 function [Network Drivers Starting with Windows Vista], O, e, fwpmk/FwpmEngineOpen0, g, i, m, n, netvista.fwpmengineopen0, p, w, wfp_ref_2_funct_2_fwpm_29969a12-e73c-4b61-b940-e0da4b0be737.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: fwpmk.h
req.include-header: Fwpmk.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows Vista.
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
req.lib: Fwpkclnt.lib
req.dll: 
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	fwpkclnt.lib
-	fwpkclnt.dll
apiname:
-	FwpmEngineOpen0
product: Windows
targetos: Windows
req.typenames: INSTANCE_PARTIAL_INFORMATION, PINSTANCE_PARTIAL_INFORMATION
---

# FwpmEngineOpen0 function


## -description


The 
  <b>FwpmEngineOpen0</b> function opens a session to the filter engine.
<div class="alert"><b>Note</b>  <b>FwpmEngineOpen0</b> is a specific version of <b>FwpmEngineOpen</b>. See <a href="https://msdn.microsoft.com/FBDF53E5-F7DE-4DEB-AC18-6D2BB59FE670">WFP Version-Independent Names and Targeting Specific Versions of Windows</a> for more information.</div><div> </div>

## -syntax


````
NTSTATUS NTAPI FwpmEngineOpen0(
  _In_opt_ const wchar_t                   *serverName,
  _In_           UINT32                    authnService,
  _In_opt_       SEC_WINNT_AUTH_IDENTITY_W *authIdentity,
  _In_opt_ const FWPM_SESSION0             *session,
  _Out_          HANDLE                    *engineHandle
);
````


## -parameters




### -param serverName [in, optional]

A pointer to a NULL-terminated string that specifies the standard DNS name of the system on which
     the session to the filter engine is opened. Callout drivers must specify <b>NULL</b> for this parameter.


### -param authnService [in]

The authentication service to use. For a list of valid choices for this parameter, see
     Authentication-Service Constants in the RPC section in the Microsoft Windows SDK documentation. Callout
     drivers must specify either RPC_C_AUTHN_WINNT or RPC_C_AUTHN_DEFAULT for this parameter.


### -param authIdentity [in, optional]

A pointer to a <b>SEC_WINNT_AUTH_IDENTITY_W</b> structure that contains the authentication and
     authorization credentials for accessing the filter engine. This parameter is ignored when the 
     <b>FwpmEngineOpen0</b> function is called from a callout driver. Callout drivers should set this
     parameter to <b>NULL</b>.


### -param session [in, optional]

A pointer to an 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff550083">FWPM_SESSION0</a> structure that defines
     session-specific parameters for the session being opened. This pointer is optional and can be
     <b>NULL</b>.


### -param engineHandle [out]

A pointer to a variable that receives a handle for the open session to the filter engine.


## -returns



The 
     <b>FwpmEngineOpen0</b> function returns one of the following NTSTATUS codes.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
A session to the filter engine was successfully opened. The variable pointed to by the 
       <i>engineHandle</i> parameter contains a handle for the open session.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>Other status codes</b></dt>
</dl>
</td>
<td width="60%">
An error occurred.

</td>
</tr>
</table>
 




## -remarks



A callout driver calls the 
    <b>FwpmEngineOpen0</b> function to open a session to the filter engine. A handle to an open session to the
    filter engine is a required parameter to most of the <a href="https://msdn.microsoft.com/0436f559-20e6-4199-8391-10eb7d85df23">Windows Filtering Platform</a>
<a href="https://answers.microsoft.com/en-us/windows/forum/windows_xp-performance/computer-management-storage-disk-management/f93a4e9b-5516-4e5c-9cd3-f04453ec963f"> management functions</a>.

Callout drivers normally do not need to open a session to the filter engine because callout drivers
    typically do not call any of the <a href="https://msdn.microsoft.com/0436f559-20e6-4199-8391-10eb7d85df23">Windows Filtering Platform</a> management functions.

For a callout driver to successfully open a session to the filter engine, the filter engine
    must be currently running at the time that the callout driver calls the 
    <b>FwpmEngineOpen0</b> function. A callout driver can call the 
    <a href="..\fwpmk\nf-fwpmk-fwpmbfestateget0.md">FwpmBfeStateGet0</a> function to obtain the
    current state of the filter engine. Before calling <b>FwpmBfeStateGet0</b>, the callout driver must call the 
    <a href="..\fwpmk\nf-fwpmk-fwpmbfestatesubscribechanges0.md">FwpmBfeStateSubscribeChanges0</a> function to register a callback function that will be called whenever
    there is a change in the state of the filter engine.

After a callout driver has finished accessing the filter engine, it calls the 
    <a href="..\fwpmk\nf-fwpmk-fwpmengineclose0.md">FwpmEngineClose0</a> function to close the
    open session to the filter engine.




## -see-also

<a href="..\fwpmk\nf-fwpmk-fwpmcalloutdeletebyid0.md">FwpmCalloutDeleteById0</a>



<a href="..\fwpmk\nf-fwpmk-fwpmcalloutadd0.md">FwpmCalloutAdd0</a>



<a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/calling-other-windows-filtering-platform-functions">Other Windows Filtering
   Platform Functions</a>



<a href="..\fwpmk\nf-fwpmk-fwpmengineclose0.md">FwpmEngineClose0</a>



<a href="..\fwpmk\nf-fwpmk-fwpmbfestateget0.md">FwpmBfeStateGet0</a>



<a href="..\fwpmk\nf-fwpmk-fwpmbfestatesubscribechanges0.md">
   FwpmBfeStateSubscribeChanges0</a>



<a href="..\fwpmk\nf-fwpmk-fwpmcalloutdeletebykey0.md">FwpmCalloutDeleteByKey0</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20FwpmEngineOpen0 function%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

