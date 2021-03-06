# Created by: Jean-Sébastien Pédron <dumbbell@FreeBSD.org>
# $FreeBSD$

PORTVERSION=	1.33.0.${NIGHTLY_DATE:C,-,,g}
PKGNAMESUFFIX=	-nightly
DISTNAME=	rustc-nightly-src

PATCH_SITES=	https://github.com/rust-lang/${PORTNAME}/commit/
PATCHFILES=	49337938cb78.patch:-p1

MASTERDIR=	${.CURDIR}/../rust
PATCHDIR=	${.CURDIR}/files
DISTINFO_FILE=	${.CURDIR}/distinfo

CONFLICTS_INSTALL=	rust

# Which source to pull:
#   https://static.rust-lang.org/dist/${NIGHTLY_DATE}/rustc-nightly-src.tar.gz
#   https://static.rust-lang.org/dist/channel-rust-nightly.toml
NIGHTLY_DATE=			2019-01-05
NIGHTLY_SUBDIR=			${NIGHTLY_DATE}/

# See WRKSRC/src/stage0.txt for this date
BOOTSTRAPS_DATE=		2018-12-09
RUST_BOOTSTRAP_VERSION=		beta
CARGO_BOOTSTRAP_VERSION=	beta

CARGO_VENDOR_DIR=	${WRKSRC}/vendor

# Other bootstraps aren't provided by upstream yet
ONLY_FOR_ARCHS=			amd64 i386

post-patch:	nightly-post-patch
nightly-post-patch:
# Work around unused_unsafe errors in libcore with stage0
# https://github.com/rust-lang/rust/pull/57184
	@${REINPLACE_CMD} '/RUSTC_DENY_WARNINGS/d' ${WRKSRC}/src/bootstrap/builder.rs

post-configure:	nightly-post-configure
nightly-post-configure:
# Don't abort if optional tools fail to build
# https://github.com/rust-lang/rust/commit/53254a888b42
	@${ECHO_CMD} 'missing-tools = true' >>${WRKSRC}/config.toml

.include "${MASTERDIR}/Makefile"
