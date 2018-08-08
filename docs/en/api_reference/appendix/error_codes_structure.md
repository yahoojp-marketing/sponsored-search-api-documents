# Reorganize error codes structure

## Overview
To improve error codes structure, following reorganization has been made.

### 1．Revise error codes structure
#### Issue: Redundant error codes and messages
* example: Same error message, but differentiate upper/lower cases.
<table class="standard">
<tbody>
<tr>
<th>Code</th>
<th>Message</th>
</tr>
<tr>
 <td valign="top">0007</td>
 <td valign="top">invalid number format.</td>
</tr>
<tr>
 <td valign="top">20601</td>
 <td valign="top">INVALID_NUMBER_FORMAT</td>
</tr>
</table>

* example: Same error message, but differentiate services such as CampaignService, AdGroupService.
<table class="standard">
<tbody>
<tr>
<th>Code</th>
<th>Message</th>
</tr>
<tr>
 <td valign="top">210305</td>
 <td valign="top">Auto bidding is already set.</td>
</tr>
<tr>
 <td valign="top">210404</td>
 <td valign="top">Auto bidding is already set.</td>
</tr>
</table>

#### Changes
* Reorganized simple errors (such as 'required', 'invalid', etc.) to some categories. 
<table class="standard">
<tbody>
<tr>
<th>Pattern</th>
<th>Category</th>
<th>Code</th>
<th>Message</th>
<th>Description</th>
</tr>
<tr>
 <td valign="top" rowspan=2>1</td>
 <td valign="top" rowspan=2>Invalid format</td>
 <td valign="top">F0001</td>
 <td valign="top">Invalid format.</td>
 <td valign="top">Invalid format of date, number, string.</td>
</tr>
<tr>
 <td valign="top">F0002</td>
 <td valign="top">Invalid file format.</td>
 <td valign="top">The format of uploading file is invalid.</td>
</tr>
<tr>
 <td valign="top">2</td>
 <td valign="top">Required</td>
 <td valign="top">R0001</td>
 <td valign="top">Require.</td>
 <td valign="top">Missing entry on required items.</td>
</tr>
<tr>
 <td valign="top" rowspan=3>3</td>
 <td valign="top" rowspan=3>Invalid value</td>
 <td valign="top">V0001</td>
 <td valign="top">Invalid value.</td>
 <td valign="top">The value with unacceptable character, date, number ENUM.</td>
</tr>
<tr>
 <td valign="top">V0002</td>
 <td valign="top">Empty file</td>
 <td valign="top">The size of uploading file is zero byte.</td>
</tr>
<tr>
 <td valign="top">V0003</td>
 <td valign="top">Over limit of the file</td>
 <td valign="top">The size of uploading file exceeds the maximum limit.</td>
</tr>
<tr>
 <td valign="top" rowspan=2>4</td>
 <td valign="top" rowspan=2>Invalid array</td>
 <td valign="top">L0001</td>
 <td valign="top">Lower list size.</td>
 <td valign="top">The number of elements of array is lower than the minumum value.</td>
</tr>
<tr>
 <td valign="top">L0002</td>
 <td valign="top">Over list size.</td>
 <td valign="top">The number of elements of array exceeds the mazimum value.</td>
</tr>
<tr>
 <td valign="top" rowspan=2>5</td>
 <td valign="top" rowspan=2>URL</td>
 <td valign="top">L0001</td>
 <td valign="top">Url has expired.</td>
 <td valign="top">The validity period of URL for upload/download is expired.</td>
</tr>
<tr>
 <td valign="top">U0002</td>
 <td valign="top">Invalid url.</td>
 <td valign="top">Unavailable URL for upload/download. <br> (altered URL, etc.)</td>
</tr>
<tr>
 <td valign="top">6</td>
 <td valign="top">Invalid status</td>
 <td valign="top">S0001</td>
 <td valign="top">Invalid Status.</td>
 <td valign="top">Invalid status. It cannot be edited or removed.</td>
</tr>
<tr>
 <td valign="top">7</td>
 <td valign="top">Deactivated ID</td>
 <td valign="top">I0001</td>
 <td valign="top">Deactivated Id.</td>
 <td valign="top">Specifying ID for an entity already removed or does not exist.</td>
</tr>
<tr>
 <td valign="top">8</td>
 <td valign="top">Duplicated</td>
 <td valign="top">D0001</td>
 <td valign="top">Duplicate.</td>
 <td valign="top">・Duplicating an item to uniquely identify entity.<br>
・Duplicating name, the name has been already registered.<br>
・Duplicating name, the name has been already used in the operand specified by request.</td>
</tr>
<tr>
 <td valign="top">9</td>
 <td valign="top">Invalid relation</td>
 <td valign="top">RL001</td>
 <td valign="top">Invalid relation.</td>
 <td valign="top">Relation of items specified on request is contradictory.<br> (For example, relation between start date and end date, etc.)</td>
</tr>
<tr>
 <td valign="top">10</td>
 <td valign="top">Over limit</td>
 <td valign="top">LT001</td>
 <td valign="top">Over limit.</td>
 <td valign="top">Exceeding the maximum number of available entities.</td>
</tr>
</table>

* Merged error codes for same message.
<table class="standard">
<tbody>
<tr>
<th>Code</th>
<th>Message</th>
<th>Deleted</th>
<th>Merged to</th>
</tr>
<tr>
 <td valign="top">210305</td>
 <td valign="top">Auto bidding is already set.</td>
 <td valign="top"></td>
 <td valign="top"></td>
</tr>
<tr>
 <td valign="top">210404</td>
 <td valign="top">Auto bidding is already set.</td>
 <td valign="top">v</td>
 <td valign="top">210305</td>
</tr>
<tr>
 <td valign="top">210405</td>
 <td valign="top">Budget has exceeded.</td>
 <td valign="top"></td>
 <td valign="top"></td>
</tr>
<tr>
 <td valign="top">210507</td>
 <td valign="top">Budget has exceeded.</td>
 <td valign="top">v</td>
 <td valign="top">210405</td>
</tr>
<tr>
 <td valign="top">210306</td>
 <td valign="top">Cannot use conversion optimizer.</td>
 <td valign="top"></td>
 <td valign="top"></td>
</tr>
<tr>
 <td valign="top">210406</td>
 <td valign="top">Cannot use conversion optimizer.</td>
 <td valign="top">v</td>
 <td valign="top">210306</td>
</tr>
<tr>
 <td valign="top">210511</td>
 <td valign="top">Cannot use conversion optimizer.</td>
 <td valign="top">v</td>
 <td valign="top">210306</td>
</tr>
<tr>
 <td valign="top">210400</td>
 <td valign="top">Double setting in Auto bidding.</td>
 <td valign="top"></td>
 <td valign="top"></td>
</tr>
<tr>
 <td valign="top">210500</td>
 <td valign="top">Double setting in Auto bidding.</td>
 <td valign="top">v</td>
 <td valign="top">210400</td>
</tr>
<tr>
 <td valign="top">210303</td>
 <td valign="top">Invalid conversion tracking.</td>
 <td valign="top"></td>
 <td valign="top"></td>
</tr>
<tr>
 <td valign="top">210402</td>
 <td valign="top">Invalid conversion tracking.</td>
 <td valign="top">v</td>
 <td valign="top">210303</td>
</tr>
<tr>
 <td valign="top">210502</td>
 <td valign="top">Invalid conversion tracking.</td>
 <td valign="top">v</td>
 <td valign="top">210303</td>
</tr>
<tr>
 <td valign="top">210304</td>
 <td valign="top">Not enough conversions or invalid setting.</td>
 <td valign="top"></td>
 <td valign="top"></td>
</tr>
<tr>
 <td valign="top">210403</td>
 <td valign="top">Not enough conversions or invalid setting.</td>
 <td valign="top">v</td>
 <td valign="top">210304</td>
</tr>
<tr>
 <td valign="top">210503</td>
 <td valign="top">Not enough conversions or invalid setting.</td>
 <td valign="top">v</td>
 <td valign="top">210304</td>
</tr>
<tr>
 <td valign="top">210308</td>
 <td valign="top">Set campaign active.</td>
 <td valign="top"></td>
 <td valign="top"></td>
</tr>
<tr>
 <td valign="top">210407</td>
 <td valign="top">Set campaign active.</td>
 <td valign="top">v</td>
 <td valign="top">210308</td>
</tr>
<tr>
 <td valign="top">210512</td>
 <td valign="top">Set campaign active.</td>
 <td valign="top">v</td>
 <td valign="top">210308</td>
</tr>
<tr>
 <td valign="top">210309</td>
 <td valign="top">Set campaign to Manual CPC.</td>
 <td valign="top"></td>
 <td valign="top"></td>
</tr>
<tr>
 <td valign="top">210408</td>
 <td valign="top">Set campaign to Manual CPC.</td>
 <td valign="top">v</td>
 <td valign="top">210309</td>
</tr>
<tr>
 <td valign="top">210513</td>
 <td valign="top">Set campaign to Manual CPC.</td>
 <td valign="top">v</td>
 <td valign="top">210309</td>
</tr>
<tr>
 <td valign="top">210301</td>
 <td valign="top">Setting the disabled Auto bidding.</td>
 <td valign="top"></td>
 <td valign="top"></td>
</tr>
<tr>
 <td valign="top">210401</td>
 <td valign="top">Setting the disabled Auto bidding.</td>
 <td valign="top">v</td>
 <td valign="top">210301</td>
</tr>
<tr>
 <td valign="top">210501</td>
 <td valign="top">Setting the disabled Auto bidding.</td>
 <td valign="top">v</td>
 <td valign="top">210301</td>
</tr>
<tr>
 <td valign="top">1000</td>
 <td valign="top">creating downloadUrl is failed.</td>
 <td valign="top">v</td>
 <td valign="top"></td>
</tr>
<tr>
 <td valign="top">2000</td>
 <td valign="top">creating bulk downloadUrl is failed.</td>
 <td valign="top">v</td>
 <td valign="top"></td>
</tr>
</table>

### 2．Deleted error codes not in use
Following error codes currently unused have been deleted.
<table class="standard">
<tbody>
<tr>
<th>Code</th>
<th>Message</th>
</tr>
<tr>
 <td valign="top">210103</td>
 <td valign="top">UNMATCH PLACEHOLDER TYPE</td>
</tr>
<tr>
 <td valign="top">210506</td>
 <td valign="top">Invalid keyword settings.</td>
</tr>
<tr>
 <td valign="top">240007</td>
 <td valign="top">Is Not Template.</td>
</tr>
</table>

## List of merged error codes
The list of merged error codes can be downloaded with the following link.<br>
[Error code strucrure (Sponsored Search API)](https://s.yimg.jp/images/promotionalads_edit/support/pdf/api_doc/error_codes_structure_SS_en.pdf)


