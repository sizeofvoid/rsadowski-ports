COMMENT =	library for parsing CSS using the Rust cssparser crate

VERSION =	1.0.0
DISTNAME =	cxx-rust-cssparser-${VERSION}

SHARED_LIBS +=	cxx-rust-cssparser        0.0 # 0.0

DIST_TUPLE +=		kde libraries cxx-rust-cssparser v${VERSION} .

CATEGORIES =	devel

# BSD, CCO, LGPLv2, LGPLv2.1
PERMIT_PACKAGE =	Yes

MODULES =		devel/cmake \
			devel/cargo

MODCARGO_BUILD =	No
MODCARGO_INSTALL =	No

MODCARGO_CARGOTOML =	${WRKSRC}/rust/Cargo.toml

BUILD_DEPENDS =		devel/corrosion


CONFIGURE_ENV +=	CARGO_HOME=${WRKDIR}/cargo-home
MAKE_ENV +=		CARGO_HOME=${WRKDIR}/cargo-home

CONFIGURE_ARGS +=	-DINSTALLED_CXXBRIDGE=${LOCALBASE}/bin/cxxbridge-cmd

WRKDIST =		${WRKDIR}/cxx-rust-cssparser-v${VERSION}-2c5cd92c14164e6da2b98beba1edeaecdc1445d1

pre-configure:
	mkdir -p ${WRKDIR}/cargo-home
	printf '%s\n' \
		'[source.crates-io]' \
		'replace-with = "modcargo"' \
		'[source.modcargo]' \
		'directory = "${MODCARGO_VENDOR_DIR}"' \
		'[net]' \
		'offline = true' \
		> ${WRKDIR}/cargo-home/config.toml

.include "crates.inc"

.include <bsd.port.mk>
