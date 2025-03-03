## API Report File for "@apollo/client"

> Do not edit this file. It is a report generated by [API Extractor](https://api-extractor.com/).

```ts

import type { ASTNode } from 'graphql';
import type { DocumentNode } from 'graphql';
import type { ExecutionResult } from 'graphql';
import type { GraphQLError } from 'graphql';
import { InvariantError } from 'ts-invariant';
import { Observable } from 'zen-observable-ts';
import type { Observer } from 'zen-observable-ts';
import { print as print_3 } from 'graphql';

// @public (undocumented)
class ApolloLink {
    constructor(request?: RequestHandler);
    // (undocumented)
    static concat(first: ApolloLink | RequestHandler, second: ApolloLink | RequestHandler): ApolloLink;
    // (undocumented)
    concat(next: ApolloLink | RequestHandler): ApolloLink;
    // (undocumented)
    static empty(): ApolloLink;
    // Warning: (ae-forgotten-export) The symbol "GraphQLRequest" needs to be exported by the entry point index.d.ts
    // Warning: (ae-forgotten-export) The symbol "FetchResult" needs to be exported by the entry point index.d.ts
    //
    // (undocumented)
    static execute(link: ApolloLink, operation: GraphQLRequest): Observable<FetchResult>;
    // Warning: (ae-forgotten-export) The symbol "RequestHandler" needs to be exported by the entry point index.d.ts
    //
    // (undocumented)
    static from(links: (ApolloLink | RequestHandler)[]): ApolloLink;
    // (undocumented)
    protected onError(error: any, observer?: Observer<FetchResult>): false | void;
    // Warning: (ae-forgotten-export) The symbol "NextLink" needs to be exported by the entry point index.d.ts
    //
    // (undocumented)
    request(operation: Operation, forward?: NextLink): Observable<FetchResult> | null;
    // (undocumented)
    setOnError(fn: ApolloLink["onError"]): this;
    // Warning: (ae-forgotten-export) The symbol "Operation" needs to be exported by the entry point index.d.ts
    //
    // (undocumented)
    static split(test: (op: Operation) => boolean, left: ApolloLink | RequestHandler, right?: ApolloLink | RequestHandler): ApolloLink;
    // (undocumented)
    split(test: (op: Operation) => boolean, left: ApolloLink | RequestHandler, right?: ApolloLink | RequestHandler): ApolloLink;
}

// @public (undocumented)
interface Body_2 {
    // (undocumented)
    extensions?: Record<string, any>;
    // (undocumented)
    operationName?: string;
    // (undocumented)
    query?: string;
    // (undocumented)
    variables?: Record<string, any>;
}

// @public (undocumented)
export const checkFetcher: (fetcher: WindowOrWorkerGlobalScope["fetch"] | undefined) => void;

// @public (undocumented)
export type ClientParseError = InvariantError & {
    parseError: Error;
};

// Warning: (ae-forgotten-export) The symbol "ApolloLink" needs to be exported by the entry point index.d.ts
//
// @public (undocumented)
export const createHttpLink: (linkOptions?: HttpOptions) => ApolloLink;

// @public (undocumented)
export const createSignalIfSupported: () => {
    controller: boolean;
    signal: boolean;
} | {
    controller: AbortController;
    signal: AbortSignal;
};

// @public (undocumented)
interface DefaultContext extends Record<string, any> {
}

// Warning: (ae-forgotten-export) The symbol "Printer" needs to be exported by the entry point index.d.ts
//
// @public (undocumented)
export const defaultPrinter: Printer;

// Warning: (ae-forgotten-export) The symbol "ExecutionPatchResultBase" needs to be exported by the entry point index.d.ts
//
// @public (undocumented)
interface ExecutionPatchIncrementalResult<TData = Record<string, any>, TExtensions = Record<string, any>> extends ExecutionPatchResultBase {
    // (undocumented)
    data?: never;
    // (undocumented)
    errors?: never;
    // (undocumented)
    extensions?: never;
    // Warning: (ae-forgotten-export) The symbol "IncrementalPayload" needs to be exported by the entry point index.d.ts
    //
    // (undocumented)
    incremental?: IncrementalPayload<TData, TExtensions>[];
}

// @public (undocumented)
interface ExecutionPatchInitialResult<TData = Record<string, any>, TExtensions = Record<string, any>> extends ExecutionPatchResultBase {
    // (undocumented)
    data: TData | null | undefined;
    // (undocumented)
    errors?: ReadonlyArray<GraphQLError>;
    // (undocumented)
    extensions?: TExtensions;
    // (undocumented)
    incremental?: never;
}

// Warning: (ae-forgotten-export) The symbol "ExecutionPatchInitialResult" needs to be exported by the entry point index.d.ts
// Warning: (ae-forgotten-export) The symbol "ExecutionPatchIncrementalResult" needs to be exported by the entry point index.d.ts
//
// @public (undocumented)
type ExecutionPatchResult<TData = Record<string, any>, TExtensions = Record<string, any>> = ExecutionPatchInitialResult<TData, TExtensions> | ExecutionPatchIncrementalResult<TData, TExtensions>;

// @public (undocumented)
interface ExecutionPatchResultBase {
    // (undocumented)
    hasNext?: boolean;
}

// @public (undocumented)
export const fallbackHttpConfig: {
    http: HttpQueryOptions;
    headers: {
        accept: string;
        "content-type": string;
    };
    options: {
        method: string;
    };
};

// Warning: (ae-forgotten-export) The symbol "SingleExecutionResult" needs to be exported by the entry point index.d.ts
// Warning: (ae-forgotten-export) The symbol "ExecutionPatchResult" needs to be exported by the entry point index.d.ts
//
// @public (undocumented)
type FetchResult<TData = Record<string, any>, TContext = Record<string, any>, TExtensions = Record<string, any>> = SingleExecutionResult<TData, TContext, TExtensions> | ExecutionPatchResult<TData, TExtensions>;

// @public (undocumented)
interface GraphQLRequest<TVariables = Record<string, any>> {
    // Warning: (ae-forgotten-export) The symbol "DefaultContext" needs to be exported by the entry point index.d.ts
    //
    // (undocumented)
    context?: DefaultContext;
    // (undocumented)
    extensions?: Record<string, any>;
    // (undocumented)
    operationName?: string;
    // (undocumented)
    query: DocumentNode;
    // (undocumented)
    variables?: TVariables;
}

// @public (undocumented)
interface HttpConfig {
    // (undocumented)
    credentials?: any;
    // (undocumented)
    headers?: Record<string, string>;
    // (undocumented)
    http?: HttpQueryOptions;
    // (undocumented)
    options?: any;
}

// @public (undocumented)
export class HttpLink extends ApolloLink {
    constructor(options?: HttpOptions);
    // (undocumented)
    options: HttpOptions;
    // (undocumented)
    requester: RequestHandler;
}

// @public (undocumented)
export interface HttpOptions {
    // (undocumented)
    credentials?: string;
    // (undocumented)
    fetch?: WindowOrWorkerGlobalScope["fetch"];
    // (undocumented)
    fetchOptions?: any;
    // (undocumented)
    headers?: Record<string, string>;
    // (undocumented)
    includeExtensions?: boolean;
    // (undocumented)
    includeUnusedVariables?: boolean;
    // (undocumented)
    preserveHeaderCase?: boolean;
    // (undocumented)
    print?: Printer;
    // (undocumented)
    uri?: string | UriFunction;
    // (undocumented)
    useGETForQueries?: boolean;
}

// @public (undocumented)
interface HttpQueryOptions {
    // (undocumented)
    includeExtensions?: boolean;
    // (undocumented)
    includeQuery?: boolean;
    // (undocumented)
    preserveHeaderCase?: boolean;
}

// @public (undocumented)
interface IncrementalPayload<TData, TExtensions> {
    // (undocumented)
    data: TData | null;
    // (undocumented)
    errors?: ReadonlyArray<GraphQLError>;
    // (undocumented)
    extensions?: TExtensions;
    // (undocumented)
    label?: string;
    // Warning: (ae-forgotten-export) The symbol "Path" needs to be exported by the entry point index.d.ts
    //
    // (undocumented)
    path: Path;
}

// @public (undocumented)
type NextLink = (operation: Operation) => Observable<FetchResult>;

// @public (undocumented)
interface Operation {
    // (undocumented)
    extensions: Record<string, any>;
    // (undocumented)
    getContext: () => DefaultContext;
    // (undocumented)
    operationName: string;
    // (undocumented)
    query: DocumentNode;
    // (undocumented)
    setContext: (context: DefaultContext) => DefaultContext;
    // (undocumented)
    variables: Record<string, any>;
}

// @public (undocumented)
export function parseAndCheckHttpResponse(operations: Operation | Operation[]): (response: Response) => Promise<any>;

// @public (undocumented)
type Path = ReadonlyArray<string | number>;

// @public (undocumented)
const print_2: typeof print_3;

// @public (undocumented)
interface Printer {
    // Warning: (ae-forgotten-export) The symbol "print_2" needs to be exported by the entry point index.d.ts
    //
    // (undocumented)
    (node: ASTNode, originalPrint: typeof print_2): string;
}

// @public (undocumented)
type RequestHandler = (operation: Operation, forward: NextLink) => Observable<FetchResult> | null;

// Warning: (ae-forgotten-export) The symbol "Body_2" needs to be exported by the entry point index.d.ts
//
// @public (undocumented)
export function rewriteURIForGET(chosenURI: string, body: Body_2): {
    parseError: any;
    newURI?: undefined;
} | {
    newURI: string;
    parseError?: undefined;
};

// Warning: (ae-forgotten-export) The symbol "HttpConfig" needs to be exported by the entry point index.d.ts
//
// @public (undocumented)
export function selectHttpOptionsAndBody(operation: Operation, fallbackConfig: HttpConfig, ...configs: Array<HttpConfig>): {
    options: HttpConfig & Record<string, any>;
    body: Body_2;
};

// @public (undocumented)
export function selectHttpOptionsAndBodyInternal(operation: Operation, printer: Printer, ...configs: HttpConfig[]): {
    options: HttpConfig & Record<string, any>;
    body: Body_2;
};

// @public (undocumented)
export const selectURI: (operation: Operation, fallbackURI?: string | ((operation: Operation) => string) | undefined) => any;

// @public (undocumented)
export const serializeFetchParameter: (p: any, label: string) => string;

// @public (undocumented)
export type ServerParseError = Error & {
    response: Response;
    statusCode: number;
    bodyText: string;
};

// @public (undocumented)
interface SingleExecutionResult<TData = Record<string, any>, TContext = DefaultContext, TExtensions = Record<string, any>> extends ExecutionResult<TData, TExtensions> {
    // (undocumented)
    context?: TContext;
    // (undocumented)
    data?: TData | null;
}

// @public (undocumented)
export interface UriFunction {
    // (undocumented)
    (operation: Operation): string;
}

// Warnings were encountered during analysis:
//
// src/link/http/selectHttpOptionsAndBody.ts:128:32 - (ae-forgotten-export) The symbol "HttpQueryOptions" needs to be exported by the entry point index.d.ts

// (No @packageDocumentation comment for this package)

```
