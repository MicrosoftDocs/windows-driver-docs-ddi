---
UID: NF:ntifs.RtlCreateAcl
title: RtlCreateAcl function (ntifs.h)
description: The RtlCreateAcl routine creates and initializes an access control list (ACL).
old-location: ifsk\rtlcreateacl.htm
tech.root: ifsk
ms.assetid: d7bf1fa0-81e0-4b44-adcd-d8f629453ac8
ms.date: 04/16/2018
ms.keywords: RtlCreateAcl, RtlCreateAcl routine [Installable File System Drivers], ifsk.rtlcreateacl, ntifs/RtlCreateAcl, rtlref_0b8e6b6c-308f-4acd-b109-d6042964ea7f.xml
f1_keywords:
 - "ntifs/RtlCreateAcl"
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
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
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: <= APC_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- RtlCreateAcl
product:
- Windows
targetos: Windows
req.typenames: 
---

# RtlCreateAcl function


## -description


The <b>RtlCreateAcl</b> routine creates and initializes an access control list (ACL). 


## -parameters




### -param Acl [out]

Pointer to a caller-allocated buffer to receive the initialized ACL structure. This buffer must be at least <b>sizeof</b>(ACL),


### -param AclLength [in]

Length, in bytes, of the buffer pointed to by the <i>Acl</i> parameter. This value must be large enough to contain the ACL header and all of the access-control entries (ACE) to be stored in the ACL. See the following Remarks section for information about calculating the size of an ACL. 


### -param AclRevision

<p>ACL revision level of the ACE to be added. Windows version requirments are the following:</p>
  <table>
    <tr>
      <th>Value</th>
      <th>Meaning</th>
    </tr>
    <tr>
      <td width="40%">
        <dl>
          <dt>ACL_REVISION</dt>
        </dl>
      </td>
      <td width="60%">
        <p>The revision level valid on all Windows versions.</p>
      </td>
    </tr>
    <tr>
      <td width="40%">
        <dl>
          <dt>ACL_REVISION_DS</dt>
        </dl>
      </td>
      <td width="60%">
        <div class="alert">
          <b>Note</b>  <i>AceRevision</i> must be ACL_REVISION_DS if the ACL in <i>Acl</i> contains an object-specific ACE.</div>
        <div> </div>
      </td>
    </tr>
  </table>
  <p> </p>




## -returns



<b>RtlCreateAcl</b> can return one of the following status values:

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
The ACL was successfully created and initialized.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_BUFFER_TOO_SMALL</b></dt>
</dl>
</td>
<td width="60%">
The new ACL does not fit into the buffer at <i>Acl</i>. A larger ACL buffer is required. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
The specified revision is not current, or the value of <i>AclLength</i> is too large. 

</td>
</tr>
</table>
 




## -remarks



The ACL that is initialized by <b>RtlCreateAcl</b> contains no access control entries (ACE). This ACL is empty, as opposed to being a nonexistent ACL. If an empty ACL is applied to an object, the ACL implicitly denies all access to that object. To add ACEs to the ACL, use <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-rtladdaccessallowedace">RtlAddAccessAllowedAce</a>.

To calculate the size of an ACL, add <b>sizeof</b>(ACL) to the size of all the ACEs to be stored in the ACL. To calculate the size of an ACE, add the size of the ACE structure, such as <b>sizeof</b>(ACCESS_ALLOWED_ACE), to the length of the SID associated with the ACE, and then subtract the size of the <b>SidStart</b> member (which is part of both the ACE structure and the SID). Use the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-rtllengthsid">RtlLengthSid</a> function to get the length of a specified SID.

The following example shows how to calculate the size of an access-allowed ACE:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>sizeof (ACCESS_ALLOWED_ACE) - sizeof (ACCESS_ALLOWED_ACE.SidStart) 
        + GetLengthSid (pAceSid);</pre>
</td>
</tr>
</table></span></div>
To calculate the size of an ACL, use the following algorithm, substituting the appropriate ACE structure in the <b>sizeof</b>(ACE) expression:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>cbAcl = sizeof (ACL);
for (i = 0 ; i < nAceCount ; i++) {
    // subtract ACE.SidStart from the size
    cbAce = sizeof (ACE) - sizeof (DWORD);
    // add this ACE's SID length
    cbAce += GetLengthSid (pAceSid[i]);
    // add the length of each ACE to the total ACL length
    cbAcl += cbAce;
}</pre>
</td>
</tr>
</table></span></div>
For more information about security and access control, see the documentation on these topics in thePlatform Software Development Kit (SDK).




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_access_allowed_ace">ACCESS_ALLOWED_ACE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/ace">ACE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_acl">ACL</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-rtladdaccessallowedace">RtlAddAccessAllowedAce</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-rtllengthsid">RtlLengthSid</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_sid">SID</a>
 

 

