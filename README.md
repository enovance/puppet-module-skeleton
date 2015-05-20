Puppet modules often take on the same file system structure. The
built-in puppet-module tool makes starting modules easy, but the build
in skeleton module is very simple. This skeleton is very opinionated.
It's going to assume you're going to start out with tests (both unit and
system), that you care about the puppet style guide, test using Travis,
keep track of releases and structure your modules according to strong
conventions.

## Installation

As a feature, puppet module tool will use `~/.puppet/var/puppet-module/skeleton`
as template for its `generate` command. The files provided here are
meant to be better templates for use with the puppet module tool.

As we don't want to have our .git files and this README in our skeleton, we export it like this:

    git clone https://github.com/stackforge/puppet-module-skeleton
    cd puppet-module-skeleton
    find skeleton -type f | git checkout-index --stdin --force --prefix="$HOME/.puppet/var/puppet-module/" --

## Usage

Then just generate your new module structure like so:

    puppet module generate stackforge-<module>

Once you have your module then install the development dependencies:

    cd stackforge-<module>
    => Use msync with review.openstack.org:stackforge/puppet-modulesync-configs.git
    bundle install

## Thanks

The trick used in the installation above come from
[garethr](https://github.com/garethr/puppet-module-skeleton) module, and a few other bits
came from another excellent module skeleton from
[spiette](https://github.com/spiette/puppet-module-skeleton).
