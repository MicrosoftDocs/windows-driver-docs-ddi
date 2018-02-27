---
UID: NA:nfcradiodev
ms.assetid: a2e40268-54ff-3618-9467-4f9e48215b04
ms.author: windowsdriverdev
ms.date: 02/26/18
ms.keywords: 
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: portal
---

# Nfcradiodev.h header



This header is used by Near field communications (NFC). For more information, see
- [Near field communications (NFC)](../_nfpdrivers/index.md)

The Radio Management DDI allows callers to the NFC device driver to set the power state of the proximity and secure element radios of the NFC device.

## Radio management DDI overview

<table>
<tr>
<th>Usage</th>
<th>DDI</th>
</tr>
<tr>
<td><b>NFP radio manager interface</b>: These IOCTLs are used to manage the radio state of proximity device. The default radio state of the proximity device is enabled/active. The radio states are persisted across boots.</td>
<td>
<dl>
<dd>
<mshelp:link tabindex="0" keywords="nfpdrivers.ioctl_nfcrm_set_radio_state"><b>IOCTL_NFCRM_SET_RADIO_STATE</b></mshelp:link>
</dd>
<dd>
<mshelp:link tabindex="0" keywords="nfpdrivers._nfcrm_set_radio_state_"><b>NFCRM_SET_RADIO_STATE</b></mshelp:link>
</dd>
<dd>
<mshelp:link tabindex="0" keywords="nfpdrivers.ioctl_nfcrm_query_radio_state"><b>IOCTL_NFCRM_QUERY_RADIO_STATE</b></mshelp:link>
</dd>
<dd>
<mshelp:link tabindex="0" keywords="nfpdrivers._nfcrm_radio_state_"><b>NFCRM_RADIO_STATE</b></mshelp:link>
</dd>
</dl>
</td>
</tr>
<tr>
<td><b>SE radio manager interface</b>: The default radio state of the SE device is enabled/active. The radio states are persisted across boots. </td>
<td>
<dl>
<dd>
<mshelp:link tabindex="0" keywords="nfpdrivers.ioctl_nfcserm_set_radio_state"><b>IOCTL_NFCSERM_SET_RADIO_STATE</b></mshelp:link>
</dd>
<dd>
<mshelp:link tabindex="0" keywords="nfpdrivers.ioctl_nfcserm_query_radio_state"><b>IOCTL_NFCSERM_QUERY_RADIO_STATE</b></mshelp:link>
</dd>
</dl>
</td>
</tr>
</table>

## Related topics

Send comments about this topic to Microsoft

