{
    html heading: count.
    html anchor
        callback: [ self increase ];
        with: '++'.
    html space.
    html anchor
        callback: [ self decrease ];
        with: '--'
    with: [ 
        html span class: 'item'; with: 'Item 1'.
        html span class: 'item'; with: 'Item 2' ]
    <span class="item">Item 1</span>
    <span class="item">Item 2</span>
</div>
    id: 'list'; 
    with: [
        1 to: 5 do: [ :i |
            html listItem 
                class: 'item'; 
                with: 'Item ', i asString ]]
    <li class="item">Item 1</li>
    <li class="item">Item 2</li>
    <li class="item">Item 3</li>
    <li class="item">Item 4</li>
    <li class="item">Item 5</li>
</ul>
    id: 'list'; 
    with: [
        1 to: 5 do: [ :i |
            html listItem 
                class: 'itemodd' if: i odd; 
                class: 'itemeven' if: i even; 
                with: 'Item ', i asString ]]
    <li class="itemodd" >Item 1</li>
     <li class="itemeven">Item 2</li>
     <li class="itemodd" >Item 3</li>
     <li class="itemeven">Item 4</li>
     <li class="itemodd" >Item 5</li>
</ul>
    html heading level: 2; with: 'Examples'.					
    html tbsAlert beSuccess;
        with: [ html strong: 'Well done!'. html text: ' You successfully read this important alert message.' ].
    html tbsAlert beInfo;
        with: [ html strong: 'Heads up!'. html text: ' This alert needs your attention, but it''s not super important.' ].
    html tbsButtonGroup: [ 
        html tbsButton beDefault; with: 'Left'.
        html tbsButton beDefault; with: 'Middle'.
        html tbsButton beDefault; with: 'Right' ].
    instanceVariableNames: ''
    classVariableNames: ''
    package: 'Seaside-Examples-Misc'
    "self initialize"
    | app |
    app := WAAdmin register: self asApplicationAt: 'twittercounter'.
    app 
        addLibrary: JQDeploymentLibrary;
        addLibrary: TBSDevelopmentLibrary
    html tbsContainer: [ 
        html form: [ 
            html tbsButtonGroup beSmall; with: [ 	
                html tbsButton beDefault; 
                    callback: [ self increase ]; with: '+'.
                html tbsButton beDefault; 
                    callback: [ self decrease ]; with: '-' ].
            html 
                space; 
                tbsBadge: self count ] ]
    html tbsContainer: [ 
         html form: [ 
             "..."
             html space.
             html tbsBadge
                 class: 'odd' if: self count odd;
                 with: self count ] ]

WATwitterCounter >> style
    ^ '.odd { color: red; }'