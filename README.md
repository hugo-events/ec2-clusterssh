# Ec2::Clusterssh

Use instance tags to launch a ClusterSSH session to multiple EC2 instances.

## Installation

    $ gem install ec2-clusterssh

## Prerequisites

- [ClusterSSH](http://sourceforge.net/apps/mediawiki/clusterssh/index.php?title=Main_Page)
- Set up your AWS credentials (note that these values can be also passed in
  as command line options)

> export AWS_ACCESS_KEY_ID='...'
> export AWS_SECRET_ACCESS_KEY='...'
> export AWS_REGION='us-west-2'

- Edit /etc/csshrc to add the path to your identity file (rsa key).

> ssh_args = "-i path/to/identity/file"

## Usage

    $cluster -h
    Usage: cluster [-t TAG -l USER] -v VALUES
        -l, --user [USER]                User to log in as (default: ec2-user)
        -t, --tag [TAG]                  TAG to filter on (default: role)
        -v, --values [VALUES]            a comma separated (no spaces) of values to match against (i.e. web,database)


    $cluster -l ec2-user -t Name -v web,database

## Contributing

1. Fork it
2. Create your feature branch (`git checkout -b my-new-feature`)
3. Commit your changes (`git commit -am 'Add some feature'`)
4. Push to the branch (`git push origin my-new-feature`)
5. Create new Pull Request
