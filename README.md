# aws-building-blocks

AWS Building blocks is a concept, expressed below, designed to help developers building on AWS Collaberate through being able to share units of functionality.  These units of functionality are known as `Building Blocks`, and are defined below

## Definition of an AWS Building Block

In the model expressed here everthing, from application functionality, deployment pipeline tooling, css styling and so on (i.e. _everything_) is encapsulated within a Building Block.

A Building Block is a a self-contained unit of functionality that is designed to achieve a single, specific purpose, and:

- accepts a single input (e.g. an event) and results in a single outcome (e.g. a component is rendered, a web page is rendered, a Lambda function is updated, emails are sent and so on)

- is inter-operable with other AWS Building Block modules.  The module is aware of other compatible building blocks and doesn't seek to re-invent the wheel but rather usiteracts with other AWS Building Blocks, improving these as needed

- is self-sufficient.  That is the Building Block has no dependencies on software other than what is fully contained in the module itself (after install) and the framework / tooling the module is built on (e.g. nodejs, terraform etc).  Because 'no module is an island' modules will often rely on other services, these dependencies need to be services interacted with over http(s), not additional software the user must install through a separate process.  These dependencies should be clearly called out in the readme

- is open-source.  

- has one or more contributers who support and improve the module through its life-cycle

- is documented, including instructions on how to install the building block on a local development machine, as well as how to install and configure the module in the AWS environment

- resides in a single code repository (e.g. a single github repo)

- is small.  Of course 'small' is subjective - the point being that 'less is more' when it comes to module authoring.

- is hosting, production and support aware.  The module should include instructions and optionally code (e.g. terraform, cloudformation etc scripts) which will install the module into production, fully ready to receive and process events passed in

- is responsible for handling  / logging problems encountered in its operation

- is responsible for handling its own state.  Persisting to the database as needed, the module must support a stateless architecture

## Examples

For examples of real-world AWS Building Blocks see the repos consained in this 'cjlennon' github project.  Repos beginning with `awsbb` (AWS Building Block) follow these specifications

## See also

For some patterns you may want to consider as you build AWS Building Blocks, see [patterns](patterns.md)
