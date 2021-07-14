## API Report File for "@backstage/plugin-jenkins-backend"

> Do not edit this file. It is a report generated by [API Extractor](https://api-extractor.com/).

```ts
import { CatalogClient } from '@backstage/catalog-client';
import { Config } from '@backstage/config';
import { EntityName } from '@backstage/catalog-model';
import express from 'express';
import { Logger as Logger_2 } from 'winston';

// @public (undocumented)
export function createRouter(options: RouterOptions): Promise<express.Router>;

// @public
export class DefaultJenkinsInfoProvider implements JenkinsInfoProvider {
  // (undocumented)
  static fromConfig(options: {
    config: Config;
    catalog: CatalogClient;
  }): DefaultJenkinsInfoProvider;
  // (undocumented)
  getInstance(opt: {
    entityRef: EntityName;
    jobFullName?: string;
  }): Promise<JenkinsInfo>;
  // (undocumented)
  static readonly NEW_JENKINS_ANNOTATION = 'jenkins.io/job-full-name';
  // (undocumented)
  static readonly OLD_JENKINS_ANNOTATION = 'jenkins.io/github-folder';
}

// @public (undocumented)
export interface JenkinsInfo {
  // (undocumented)
  baseUrl: string;
  // (undocumented)
  headers?: Record<string, string | string[]>;
  // (undocumented)
  jobFullName: string;
}

// @public (undocumented)
export interface JenkinsInfoProvider {
  // (undocumented)
  getInstance(options: {
    entityRef: EntityName;
    jobFullName?: string;
  }): Promise<JenkinsInfo>;
}

// @public (undocumented)
export interface RouterOptions {
  // (undocumented)
  jenkinsInfoProvider: JenkinsInfoProvider;
  // (undocumented)
  logger: Logger_2;
}

// (No @packageDocumentation comment for this package)
```