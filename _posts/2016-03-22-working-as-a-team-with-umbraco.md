---
layout: post
title:  "Working as a team with Umbraco CMS & Umbraco Courier 2"
date:   2016-03-18 20:46:00
comments: true
categories: development
---

Below is a quick summary on how to effectively work as a team with Umbraco CMS.
If you have any suggestions or improvements, please leave a comment.

Create revisions with Umbraco Courier 2, store them in Git as well as your ASP .NET MVC solution containing your Umbraco CMS installation.

Developers can work in parallel as long as the `Web.config` file points to the same database.

A single `Revision` from **Umbraco Courier 2**, containing content, can then be transferred from `Development` environment to the `Staging` environment for testing and verification.

**Feature** changes, that result in newly compiled .DLL files, templates etc. should simply be copied over via `XCOPY` or similar constructs, preferably performed via automation.

Obvious but important to mention is that **Feature** changes also must be committed to the Git repository.

Once changes are approved and new content has been added by non-developers, this content can be synchronised with the `Development` environment again via Umbraco Courier 2.

To publish, synchronise content changes from the `Staging` environment with the `Production` environment using Umbraco Courier 2. **Feature** changes
