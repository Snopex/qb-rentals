# qb-rentals
# Vehicle Rental Script for QBCore Framework

# Installation

<li>Find this in <strong>qb-target/config</strong></li>
<li>Put this in <strong>"Config.TargetModels"</strong> (more reliable to always keep target models in config)</li>
<pre>    [<span class="pl-s"><span class="pl-pds">"</span>VehicleRental<span class="pl-pds">"</span></span>] <span class="pl-k">=</span> {
        models <span class="pl-k">=</span> {
            `a_m_y_business_03`,
        },
        options <span class="pl-k">=</span> {
            {
                type <span class="pl-k">=</span> <span class="pl-s"><span class="pl-pds">"</span>client<span class="pl-pds">"</span></span>,
                event <span class="pl-k">=</span> <span class="pl-s"><span class="pl-pds">"</span>qb-rental:openMenu<span class="pl-pds">"</span></span>,
                icon <span class="pl-k">=</span> <span class="pl-s"><span class="pl-pds">"</span>fas fa-car<span class="pl-pds">"</span></span>,
                label <span class="pl-k">=</span> <span class="pl-s"><span class="pl-pds">"</span>Rent Vehicle<span class="pl-pds">"</span></span>,
            },
        },
        distance <span class="pl-k">=</span> <span class="pl-c1">4.0</span>
    },

}</pre>

# Rental Papers Item - qb-core/shared.lua

<pre class="notranslate"><code>["rentalpapers"]				 = {["name"] = "rentalpapers", 					["label"] = "Rental Papers", 			["weight"] = 0, 		["type"] = "item", 		["image"] = "rentalpapers.png", 		["unique"] = true, 		["useable"] = false, 	["shouldClose"] = false, 	["combinable"] = nil, 	["description"] = "Yea, this is my car i can prove it!"},
</code></pre>

# Rental Papers Item Description - qb-inventory/html/js/app.js (Line 577)
<pre>        } <span class="pl-k">else</span> <span class="pl-k">if</span> (itemData.<span class="pl-smi">name</span> <span class="pl-k">==</span> <span class="pl-s"><span class="pl-pds">"</span>stickynote<span class="pl-pds">"</span></span>) {
            $(<span class="pl-s"><span class="pl-pds">"</span>.item-info-title<span class="pl-pds">"</span></span>).<span class="pl-c1">html</span>(<span class="pl-s"><span class="pl-pds">'</span>&lt;p&gt;<span class="pl-pds">'</span></span> <span class="pl-k">+</span> itemData.<span class="pl-smi">label</span> <span class="pl-k">+</span> <span class="pl-s"><span class="pl-pds">'</span>&lt;/p&gt;<span class="pl-pds">'</span></span>)
            $(<span class="pl-s"><span class="pl-pds">"</span>.item-info-description<span class="pl-pds">"</span></span>).<span class="pl-c1">html</span>(<span class="pl-s"><span class="pl-pds">'</span>&lt;p&gt;<span class="pl-pds">'</span></span> <span class="pl-k">+</span> itemData.<span class="pl-smi">info</span>.<span class="pl-smi">label</span> <span class="pl-k">+</span> <span class="pl-s"><span class="pl-pds">'</span>&lt;/p&gt;<span class="pl-pds">'</span></span>);
        } <span class="pl-k">else</span> <span class="pl-k">if</span> (itemData.<span class="pl-smi">name</span> <span class="pl-k">==</span> <span class="pl-s"><span class="pl-pds">"</span>rentalpapers<span class="pl-pds">"</span></span>) {
            $(<span class="pl-s"><span class="pl-pds">"</span>.item-info-title<span class="pl-pds">"</span></span>).<span class="pl-c1">html</span>(<span class="pl-s"><span class="pl-pds">'</span>&lt;p&gt;<span class="pl-pds">'</span></span> <span class="pl-k">+</span> itemData.<span class="pl-smi">label</span> <span class="pl-k">+</span> <span class="pl-s"><span class="pl-pds">'</span>&lt;/p&gt;<span class="pl-pds">'</span></span>)
            $(<span class="pl-s"><span class="pl-pds">"</span>.item-info-description<span class="pl-pds">"</span></span>).<span class="pl-c1">html</span>(<span class="pl-s"><span class="pl-pds">'</span>&lt;p&gt;&lt;strong&gt;Name: &lt;/strong&gt;&lt;span&gt;<span class="pl-pds">'</span></span><span class="pl-k">+</span> itemData.<span class="pl-smi">info</span>.<span class="pl-smi">firstname</span> <span class="pl-k">+</span> <span class="pl-s"><span class="pl-pds">'</span>&lt;/span&gt;&lt;/p&gt;&lt;p&gt;&lt;strong&gt;Last Name: &lt;/strong&gt;&lt;span&gt;<span class="pl-pds">'</span></span><span class="pl-k">+</span> itemData.<span class="pl-smi">info</span>.<span class="pl-smi">lastname</span><span class="pl-k">+</span> <span class="pl-s"><span class="pl-pds">'</span>&lt;/span&gt;&lt;/p&gt;&lt;p&gt;&lt;strong&gt;Plate: &lt;/strong&gt;&lt;span&gt;<span class="pl-pds">'</span></span><span class="pl-k">+</span> itemData.<span class="pl-smi">info</span>.<span class="pl-smi">plate</span> <span class="pl-k">+</span> <span class="pl-s"><span class="pl-pds">'</span>&lt;p&gt;&lt;strong&gt;Model: &lt;/strong&gt;&lt;span&gt;<span class="pl-pds">'</span></span><span class="pl-k">+</span> itemData.<span class="pl-smi">info</span>.<span class="pl-smi">model</span> <span class="pl-k">+</span><span class="pl-s"><span class="pl-pds">'</span>&lt;/span&gt;&lt;/p&gt;<span class="pl-pds">'</span></span>);</pre>
