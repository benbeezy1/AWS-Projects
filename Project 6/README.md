<h1>Caching Static Files with Amazon CloudFront</h1>

<h2>Description</h2>
This project demonstrates how Amazon CloudFront distributes and caches static website content from an Amazon S3 origin.
I created a CloudFront distribution, tested global delivery behavior, updated origin content, and validated cache invalidation to force refreshed content at the edge.
<br /><br />

<h2>AWS Services Used</h2>

- <b>Amazon S3</b> - static website origin content
- <b>Amazon CloudFront</b> - global content delivery and edge caching
<br />

<h2>Environments Used</h2>

- <b>AWS Management Console</b>
- <b>Code editor and web browser</b>
<br />

<h2>Project Walk-through</h2>

<p align="center">
<b>Review baseline S3-hosted page</b>: Verified the original static site content served from the bucket origin. The lab started with atatic website hosted in S3. <br/>
<img src="https://i.imgur.com/KlErCEk.png" height="80%" width="80%" alt="S3-hosted baseline page"/>
<br /><br />
</p>

<p align="center">
<b>Create CloudFront distribution plan</b>: Selected distribution setup options and proceeded with pay-as-you-go configuration. <br/>
<img src="https://i.imgur.com/m9s1rHV.png" height="80%" width="80%" alt="CloudFront choose plan"/>
<img src="https://i.imgur.com/tcbwUrd.png" height="80%" width="80%" alt="CloudFront choose plan"/>
<img src="https://i.imgur.com/TBF1JAs.png" height="80%" width="80%" alt="CloudFront choose plan"/>
<img src="https://i.imgur.com/FJcYxCE.png" height="80%" width="80%" alt="CloudFront choose plan"/>
<br /><br />
</p>

<p align="center">
<b>Review and create distribution</b>: Confirmed origin and cache behavior settings before deployment. <br/>
<img src="https://i.imgur.com/qHi722F.png" height="80%" width="80%" alt="CloudFront review and create"/>
<img src="https://i.imgur.com/zL973mW.png" height="80%" width="80%" alt="CloudFront choose plan"/>

<br /><br />
</p>

<p align="center">
<b>Test site through CloudFront domain</b>: Validated static content was delivered through the CloudFront URL. <br/>
<img src="https://i.imgur.com/K4OnMy4.png" height="80%" width="80%" alt="CloudFront content test"/>
<img src="https://i.imgur.com/6FirGr9.jpeg" height="80%" width="80%" alt="CloudFront content test"/>
<img src="https://i.imgur.com/2XmMscb.png" height="80%" width="80%" alt="CloudFront content test"/>
<br /><br />
</p>

<p align="center">
<b>Upload new versioned asset to S3</b>: Added updated static object content to prepare cache update testing. The S3 url (website) got updated with the new image but the cloudfront url still had the old image. <br/>
<img src="https://i.imgur.com/t4EoXZN.png" height="80%" width="80%" alt="Upload new object version to S3"/>
<img src="https://i.imgur.com/XX0BwXc.png" height="80%" width="80%" alt="Upload new object version to S3"/>
<img src="https://i.imgur.com/UaDbqTN.png" height="80%" width="80%" alt="Upload new object version to S3"/>
<img src="https://i.imgur.com/C7zptWw.png" height="80%" width="80%" alt="Upload new object version to S3"/>
<br /><br />
</p>

<p align="center">
<b>Deleted the html file and Observed origin and cache behavior difference </b>: S3 direct path showed an access error while CloudFront continued serving cached content. <br/>
<img src="https://i.imgur.com/wunSiNC.png" height="80%" width="80%" alt="S3 access behavior after object change"/>
<img src="https://i.imgur.com/AMzsk7h.png" height="80%" width="80%" alt="S3 access behavior after object change"/>
<img src="https://i.imgur.com/nVnQ1uA.png" height="80%" width="80%" alt="S3 access behavior after object change"/>
<br /><br />
</p>

<p align="center">
<b>Renamed a new html file to match the name of the deleted file and Observed origin and cache behavior difference </b>: S3 direct path now has a webpage with the most recent update while CloudFront continued serving cached content. <br/>
<img src="https://i.imgur.com/bJzitO0.png" height="80%" width="80%" alt="S3 access behavior after object change"/>
<img src="https://i.imgur.com/LtyhlnC.png" height="80%" width="80%" alt="S3 access behavior after object change"/>
<img src="https://i.imgur.com/nVnQ1uA.png" height="80%" width="80%" alt="S3 access behavior after object change"/>
<br /><br />
</p>


<p align="center">
<b>Create CloudFront invalidation</b>: Invalidated <code>/cf_lab1.html</code> to force edge locations to fetch updated origin content. <br/>
<img src="https://i.imgur.com/8LIUo8V.png" height="80%" width="80%" alt="Create CloudFront invalidation"/>
<img src="https://i.imgur.com/7a3UNBf.png" height="80%" width="80%" alt="Create CloudFront invalidation"/>
<br /><br />
</p>

<p align="center">
<b>Validate refreshed content</b>: Confirmed updated page content was now served through CloudFront. <br/>
<img src="https://i.imgur.com/ls5Zndu.png" height="80%" width="80%" alt="Updated content after invalidation"/>
<br /><br />
</p>

<h2>Skills Learned</h2>

- Creating and configuring CloudFront distributions for S3 origins
- Understanding edge caching behavior and stale content scenarios
- Applying cache invalidation to propagate updates globally
- Testing and validating static content delivery paths
<br />

<h2>Task Completed</h2>

- Created a CloudFront distribution for static S3 content
- Validated website delivery from CloudFront endpoint
- Updated origin assets and observed caching behavior
- Executed invalidation and verified refreshed edge content
