default_layer {
    display-name = *BASE*;
    bindings = <
    &kp Q    &kp W    &kp E    &kp R    &kp T    &kp Y    &kp U    &kp I    &kp O    &kp P
    &kp A    &kp S    &kp D    &kp F    &kp G    &kp H    &kp J    &kp K    &kp L
    &kp Z    &kp X    &kp C    &kp V    &kp B    &kp N    &kp M    &kp **BSPC**
    &kp **LGUI** &kp **LALT** &kp **SPACE** &mo 1   &mo 2    &kp **RET**
    >;
};

lower_layer {
    display-name = *LOWER*;
    bindings = <
    &kp N1   &kp N2   &kp N3   &kp N4   &kp N5   &kp N6   &kp N7   &kp N8   &kp N9   &kp N0
    &kp **EXCL** &kp AT   &kp **HASH** &kp **DLLR** &kp **PRCNT** &kp **CARET** &kp **AMPS** &kp **ASTRK** &kp **LPAR** &kp **RPAR**
    &trans   &kp **MINUS** &kp **EQUAL** &kp **LBKT** &kp **RBKT** &kp **BSLH** &kp **GRAVE**
    &trans   &trans   &trans   &trans   &mo 1    &trans
    >;
};
