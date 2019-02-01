---
UID: NF:portcls.IPortClsVersion.GetVersion
title: IPortClsVersion::GetVersion (portcls.h)
description: The GetVersion method returns the version of the Windows operating system that the driver is running on.
old-location: audio\iportclsversion_getversion.htm
tech.root: audio
ms.assetid: ce1394e5-1d45-4b59-8738-fcb2cbe7cf51
ms.date: 05/08/2018
ms.keywords: GetVersion, GetVersion method [Audio Devices], GetVersion method [Audio Devices],IPortClsVersion interface, IPortClsVersion interface [Audio Devices],GetVersion method, IPortClsVersion.GetVersion, IPortClsVersion::GetVersion, audio.iportclsversion_getversion, audmp-routines_82b73b24-296b-4b31-88e4-1d1303863c6c.xml, portcls/IPortClsVersion::GetVersion
ms.topic: method
req.header: portcls.h
req.include-header: Portcls.h
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
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	portcls.h
api_name:
-	IPortClsVersion.GetVersion
product:
- Windows
targetos: Windows
req.typenames: 
---

# IPortClsVersion::GetVersion


## -description


The <code>GetVersion</code> method returns the version of the Windows operating system that the driver is running on.


## -parameters






#### - None


## -returns



The <code>GetVersion</code> method returns a DWORD value that specifies the Windows version number. For more information, see the following Remarks section.




## -remarks



The <code>GetVersion</code> method returns version information that specifies the Windows release.

The possible Windows version numbers that <code>GetVersion</code> can return are shown in the following table.

<table>
<tr>
<th rowspan="2">Version Number</th>
<th rowspan="2">Windows Version</th>
<th>Supports</th>
</tr>
<tr>
<th>IPortClsVersion?</th>
</tr>
<tr>
<td>
<b>kVersionWin98</b>

</td>
<td>
Windows 98

</td>
<td>

        no
       

</td>
</tr>
<tr>
<td>
<b>kVersionWin98SE</b>

</td>
<td>
Windows 98 Second Edition

</td>
<td>

        no
       

</td>
</tr>
<tr>
<td>
<b>kVersionWin2K</b>

</td>
<td>
Windows 2000

</td>
<td>

        no
       

</td>
</tr>
<tr>
<td>
<b>kVersionWin98SE_QFE2</b>

</td>
<td>
Windows 98 SE + Hot-Fix Package 269601 (See <a href="https://msdn.microsoft.com/8fcdc565-9d8a-45d9-9dc2-0420cbffc4f5">Additional Requirements for Windows 98</a>.)

</td>
<td>

        no
       

</td>
</tr>
<tr>
<td>
<b>kVersionWin2K_SP2</b>

</td>
<td>
Windows 2000 + Service Pack 2

</td>
<td>
YES

</td>
</tr>
<tr>
<td>
<b>kVersionWinME</b>

</td>
<td>
Windows Me

</td>
<td>

        no
       

</td>
</tr>
<tr>
<td>
<b>kVersionWin98SE_QFE3</b>

</td>
<td>
Reserved for future use

</td>
<td>
YES

</td>
</tr>
<tr>
<td>
<b>kVersionWinME_QFE1</b>

</td>
<td>
Reserved for future use

</td>
<td>
YES

</td>
</tr>
<tr>
<td>
<b>kVersionWinXP</b>

</td>
<td>
Windows XP

</td>
<td>
YES

</td>
</tr>
<tr>
<td>
<b>kVersionWinXPSP1</b>

</td>
<td>
Windows XP + Service Pack 1

</td>
<td>
YES

</td>
</tr>
<tr>
<td>
<b>kVersionWinServer2003</b>

</td>
<td>
Windows Server 2003

</td>
<td>
YES

</td>
</tr>
<tr>
<td>
<b>kVersionWin2K_UAAQFE</b>

</td>
<td>
Windows 2000 + hot-fix package with IUnregister<i>Xxx</i> support (See <a href="https://msdn.microsoft.com/d8ebd6d9-37ed-4890-aae1-5ecf58f2e22a">Dynamic Audio Subdevices</a>.)

</td>
<td>
YES

</td>
</tr>
<tr>
<td>
<b>kVersionWinXP_UAAQFE</b>

</td>
<td>
Windows XP + hot-fix package with IUnregister<i>Xxx</i> support (See <a href="https://msdn.microsoft.com/d8ebd6d9-37ed-4890-aae1-5ecf58f2e22a">Dynamic Audio Subdevices</a>.)

</td>
<td>
YES

</td>
</tr>
<tr>
<td>
<b>kVersionWinServer2003_UAAQFE</b>

</td>
<td>
Windows Server 2003 + hot-fix package with IUnregister<i>Xxx</i> support (See <a href="https://msdn.microsoft.com/d8ebd6d9-37ed-4890-aae1-5ecf58f2e22a">Dynamic Audio Subdevices</a>.)

</td>
<td>
YES

</td>
</tr>
</table>
 

The version numbers in the preceding table are defined in header file portcls.h. Note that portcls.h defines version numbers both for Windows versions that do and do not support the <b>IPortClsVersion</b> interface. Both types of version number can be useful. A miniport driver typically contains a proprietary routine that determines the Windows version and can return any of the version numbers in the preceding table. When executed on a platform that does not support <b>IPortClsVersion</b>, this routine needs to use other software tests to determine the Windows version. These tests typically rely on the <a href="https://msdn.microsoft.com/library/windows/hardware/ff549382">IoIsWdmVersionAvailable</a> function. For a code example of such a routine, see the sb16 sample audio driver in the Windows Driver Kit (WDK).

The version numbers in the preceding table are listed in roughly chronological order. Each successive Windows version in the table does not necessarily represent a feature superset of the preceding version. For example, the version that is represented by <b>kVersionWin2K</b> has more audio features than the version that is represented by <b>kVersionWin98SE_QFE2</b>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff536877">IPortClsVersion</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549382">IoIsWdmVersionAvailable</a>
 

 

