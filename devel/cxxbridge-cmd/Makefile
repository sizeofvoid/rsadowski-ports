COMMENT =	C++ code generator for the CXX Rust/C++ FFI

PKGNAME =	cxxbridge-cmd-${V}
V =		1.0.194

DIST_TUPLE +=	github dtolnay cxx ${V} .

CATEGORIES =	devel

HOMEPAGE =	https://cxx.rs

# Apache/2.0 and MIT
PERMIT_PACKAGE =	Yes

MODULES =	devel/cargo

SEPARATE_BUILD =	Yes

CONFIGURE_STYLE =	cargo

WANTLIB +=	${MODCARGO_WANTLIB}

MODCARGO_INSTALL_TARGET_PATHS = gen/cmd

.include "crates.inc"

.include <bsd.port.mk>
