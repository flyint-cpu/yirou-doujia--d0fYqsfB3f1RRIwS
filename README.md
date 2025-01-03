
大家好，我是汤师爷\~


今天聊聊促销系统整体规划。


各类促销活动的系统流程，可以抽象为3大阶段：


* B端促销活动管理：商家运营人员在后台系统中配置和管理促销活动，包括设定活动基本信息、使用规则、选择适用商品等核心功能。
* C端促销活动参与：消费者在前台系统中浏览和参与促销活动，并在下单时获得相应的价格优惠或其他权益。
* 促销效果分析：通过促销活动的数据采集和分析功能，评估活动成效并为后续促销策略提供决策依据，重点跟踪销量提升、客单价变化和新客转化等核心指标。


由于优惠券活动在创建流程、使用规则、发放方式和核销流程上具有特殊性，我们将对其进行单独讨论。


### 促销活动系统流程


促销活动系统流程开始于活动创建，经过活动生效、前端展示，最后应用在消费者结算、下单时的价格计算上。


![](https://img2024.cnblogs.com/other/2625446/202501/2625446-20250102173910690-1045319370.jpg)


### **促销活动创建环节**


促销活动创建分为三个核心配置环节：基础信息、活动规则、活动商品及库存。


**1、基础信息**


基础信息决定促销活动的核心定位，主要包括活动名称、类型、时间周期、使用限制等。活动名称要清晰体现优惠方式，如”满100减10“、”限时秒杀“。


活动类型涵盖满减、直减、折扣、秒杀等形式。


时间周期需根据促销活动的目标、节假日需求和库存情况设置，例如双十一促销，通常持续数天至一周。


活动通常也需要设置使用限制，例如，用户限制（如仅限新用户、特定会员等级）；渠道限制（如特定区域或终端）。


对于需要精确定位目标人群的活动，应在后台系统中设置合理的人群标签分类，确保活动生效后，能准确触达特定用户群体。


**2、活动规则**


活动规则由优惠门槛和优惠内容组成，共同决定最终的促销优惠方案。


优惠门槛是指消费者需要哪些特定条件，才能获得促销优惠。通常包括：


* 消费金额门槛：例如"满300元减50元"中，300元即为金额门槛。
* 购买数量门槛：如"买三送一"中，需要购买3件商品才能获得赠品。
* 会员等级门槛：某些优惠活动可能仅限特定等级的会员参与。


设置合理的优惠门槛可以帮助商家提升客单价，同时避免过度让利影响利润，门槛的高低需要根据商品特性、市场竞争和用户消费能力来权衡。


优惠内容是指促销活动中具体给予用户的优惠形式和力度，主要包括：


* 金额减免：如满300减50、折扣8折等固定金额或比例的优惠。
* 赠品促销：购买指定商品后赠送额外商品或赠品。
* 运费优惠：免运费或运费减免等物流费用优惠。
* 组合优惠：如第二件半价、多件优惠等数量相关的优惠。


此外，在创建促销活动时，必须明确规定该活动能否与其他促销叠加使用，包括是否可以与店铺优惠、平台活动或优惠券配合使用，这项规则对防止过度优惠非常重要。


**3、活动商品与活动库存**


创建活动时，可选择全部商品、指定商品或排除某些商品参与。例如，虚拟卡券不适用某个促销活动，设置活动商品时，应在商品层面排除这些商品。为实现灵活的组合，参与活动的商品应细化到SKU粒度。


活动库存的管理包含用户维度和商品维度两个方面。用户维度通过限购来防止囤货，例如"每人限购2次"，超出限制后只能按原价购买。商品维度则控制活动总量，当库存耗尽时自动恢复原价，并下架活动。


活动库存管理在秒杀活动中格外重要。由于秒杀活动会吸引大量用户在短时间内集中抢购限量商品，系统需要精确控制库存数量以确保活动公平，并防止出现超卖问题。


**3、活动生效与结束**


活动生效时，系统会根据设定的开始时间自动触发优惠。当大量商品同时生效时，系统负载会显著上升，需提前与技术团队沟通并进行压力测试。活动结束可通过以下方式触发：


* 正常达到设定结束时间。
* 提前结束或中止，如活动库存快速售罄，无需继续维持促销。
* 人工干预撤出部分商品，如发现价格定位失误或商品损失过大，需临时取消优惠。


需要注意，活动进行中的撤销促销活动，会影响用户体验。为降低不良影响，可以通过严格的审批流程和后台权限管理进行把控。


### C端促销活动参与


C端促销活动参与是指消费者在前端参与各类促销活动的完整过程。用户可以通过多个入口了解促销信息，选择感兴趣的商品，并在下单时享受相应的价格优惠。促销活动参与的关键环节包括：


* 浏览促销信息：消费者通过首页banner、活动专题页、商品列表、商品详情等多个入口了解当前的促销活动。
* 选择商品：根据促销规则选择符合条件的商品，系统会实时展示优惠后价格。
* 确认订单：确认商品数量，系统自动计算优惠金额并显示最终支付价格。
* 完成支付：消费者支付订单后，系统会记录其享受的优惠详情。


**1\. 促销信息展示**


促销主要有以下几个位置进行展示：


* 商品详情页：按商品维度展示当前生效和即将生效的促销信息，包括促销标签、倒计时、到手价和促销说明等。即将生效的促销（如秒杀）会优先展示，并显示预计开始时间。
* 促销详情页：按促销维度展示活动时间、规则和参与商品。该页面便于消费者查找促销商品和凑单，配备搜索功能和价格排序等工具。
* 商品列表页：展示商品维度的促销标签，因展示空间受限，需设置标签优先级规则。
* 专题页：通过页面搭建模块，由运营人员手动配置和管理促销内容展示。


**2、促销计价**


促销计价是指根据设定的促销规则，计算商品在促销活动中的实际销售价格的过程。它需要考虑多个因素，包括原价、促销规则和叠加互斥等，最终得出用户实际需要支付的金额。


促销计价的核心是确保商品价格既能体现促销优惠力度，又要保证商家的合理利润。同时，促销计价还需要将促销优惠金额合理地分摊到订单中的每个商品上。这个过程对于订单售后、数据统计和财务核算都非常重要。主要包括两个关键场景：


* 售后场景：当用户申请售后时，需要准确计算应退金额，这就需要知道每个商品实际分摊了多少优惠金额。
* 数据分析：为了准确统计每个商品的实际收入和利润，需要将订单级别的优惠按照合理的规则分摊到具体商品上。


促销计价会在概念模型设计章节中详细讲解。


### 促销逆向流程


促销逆向流程是指当订单发生取消、退款或其他异常情况时，需要对已使用的促销优惠进行合理处理的一系列操作。


促销逆向流程的核心目标是确保在订单发生变化时，能够准确、及时地处理优惠资产，既要保护商家利益，又要维护用户权益。


例如，商家推出"满100元送优惠券"的活动。一位消费者下了200元订单并获得优惠券，后来申请全额退款，此时商家要求回收优惠券。另一位消费者也下了200元订单，但只申请退款50元，因为订单金额仍超过门槛，商家决定让顾客保留优惠券。


这个过程需要考虑多种复杂场景，如部分退款、分批退款等情况下的资产处理策略。


### 促销活动效果分析


活动结束后，需要对执行效果进行全面评估，关键是要将数据指标与活动目标相对应，例如：


* 如果活动目标是获取新客，重点关注新客数量和获客成本
* 如果目标是提升客单价，则重点分析订单金额分布和商品组合情况
* 如果是清理库存，则主要看目标商品的去化率和库存周转情况


在长期运营过程中，促销活动需要持续试错和优化，在用户体验和收益之间找到平衡点。


### **优惠券系统流程**


优惠券是一种常见的营销工具，本质上是商家承诺给予消费者的价格折扣凭证，具有面值、使用条件和有效期等基本属性。


优惠券系统流程主要包括优惠券模板创建、领券活动创建、C端领取使用。


活动结束后，还需要进行活动效果分析，整体可以视为一个"投放—领取—使用—复盘"的完整循环。


![](https://img2024.cnblogs.com/other/2625446/202501/2625446-20250102173911323-748911544.jpg)


### 优惠券模板创建


优惠券模板是创建和管理优惠券的基础配置单元，它定义了一类优惠券的核心属性和使用规则。通过模板，运营人员可以批量生成具有相同属性的优惠券。


优惠券模板创建时，主要包含以下核心信息：


* 展示信息：优惠券名称、面值金额、使用说明等
* 有效期规则：固定有效期、领取后N天有效等
* 使用门槛：适用商品范围、消费门槛、新客/老客、是否可与其他优惠叠加等
* 发放规则：发放总量、单用户领取限制、发放渠道、目标用户群等
* 优惠内容：满减、折扣、商品兑换等
* 预算控制：优惠总额度、承担比例等


有些系统为了让商家更容易理解，会将优惠券模板与活动信息合并在一起。


然而，从系统底层设计角度来看，将优惠券模板和活动信息分开更为合理，主要基于以下几点考虑：


**1、模块化管理，适应不同活动类型**


不同活动类型需要维护的信息各不相同。例如，领券活动需要"领取时间"、"用户限领量"等属性，而抽奖活动需要”奖品及规则设置“、”用户抽奖次数“等属性。


若将优惠券模板和活动信息合并，会导致页面和配置逻辑臃肿，难以扩展。分开后，优惠券模板只需提供券基础信息即可，各模块可专注处理自身业务，便于后续维护和开发。


**2、预算管理更灵活**


企业通常会对优惠券发放设置预算。将优惠券模板独立出来，并在创建时进行预算设置，有助于成本把控。


例如，双十一期间发放"满100减10"的券，预算10万元，限制1万张。创建后，这1万张券可在活动期间灵活发放。分开设计后，活动系统只需判断剩余可发券数量，预算核销则在优惠券模块统一处理，避免相互干扰。


**3、降低系统耦合度，减少维护成本**


优惠券的使用场景多种多样，除了常规的领券活动，还包括客服补偿、抽奖、办会员赠送等。


如果优惠券与活动信息紧密绑定，任何一方的调整都可能影响另一方，增加升级和维护难度。相反，分离式设计符合软件工程的"低耦合"原则，可大幅降低后续迭代和维护成本。


### 领券活动的创建


优惠券模板仅定义了券的基本信息、使用门槛和优惠力度。要实际将券发放给用户，还需要创建领取活动，领券活动主要规定发放方式、时间、投放渠道及目标人群。


**1、领券活动时间**


活动时间规定了用户可领取优惠券的具体时段。为确保用户体验，优惠券的有效期必须长于活动结束时间，避免用户领到已过期或即将过期的券。


**2、领券位置**


活动需要确定在哪些位置触达用户，如首页、商品页、购物车、领券中心等。不同位置的曝光效果和投放成本各异。例如，首页弹窗虽然曝光最大，但成本也最高；对于新渠道合作，还需考虑渠道自身的规则限制。


**3、发放用户**


创建活动时需要明确目标人群，精细化运营则可以通过CRM（客户运营系统）圈定具体用户群。


例如，为提升高端会员的忠诚度，可专门向VIP用户发放满200减50的大额券。但此类高价值券需要配合风控措施，防止被滥用。


**4、活动总量与领取限制**


活动需设置总发券量，并可分时段发放，避免瞬间抢光。同时设定每人领取上限，既可以确保优惠覆盖面，又能控制成本。


### C端优惠券领取和使用


从C端视角看，优惠券的核心是"领"和"用"两个动作。


**1、领取优惠券**


优惠券的领取场景主要可以分为以下两大类：


* 公开券：在领券中心、商品详情页等公共入口提供，所有用户均可领取。
* 私密券：仅能通过定向链接、兑换码或人工添加方式获得。


领取后，用户可在个人账户中，查看优惠券列表，可以根据券的状态（未使用、已使用、已过期）判断使用权限。


**2、核销优惠券**


当消费者结算订单时，系统自动匹配可用的优惠券。当多张券同时满足使用条件时，系统会展示可选列表供用户选择。


订单提交后，系统自动执行优惠券核销，将优惠券标记为已使用，并记录核销时间和订单信息，以供后续数据分析。


**3、售后返还**


售后流程涉及优惠券返还政策，这是一个需要仔细考虑的重要环节。系统需要根据具体的退款情况和优惠券使用状态来执行相应的返还规则。常见的规则如下：


* 已过期的券不予返还。
* 订单全部退款时，优惠券返还至用户账户并重新激活。
* 部分退货但剩余商品仍满足使用条件时，不予返还优惠券，以防止重复使用。


这些流程需要与售后系统密切配合，监控售后原因和时间，同时对频繁退券行为进行风控。


### **促销系统核心功能**


通过上述的促销系统流程分析，我们已经了解了促销系统的核心要素和关键流程。促销系统的核心功能模块可以抽象为三大板块：促销活动管理、C端促销活动参与和促销效果分析。


* 促销活动管理：活动创建与规则配置、活动审核与发布、活动状态管理等。
* C端促销活动参与：活动页装修与展示、购物车（凑单、分组、优惠计算）、下单并支付（用券、抵扣、权益返还、优惠计算）等。
* 促销效果分析：数据采集、用户转化分析、ROI分析、报表导出等。



> 本文已收录于，我的技术网站：[tangshiye.cn](https://github.com) 里面有，AI 编程、算法 Leetcode 详解、面试八股文、BAT面试真题、简历模版、架构设计，等经验分享。


 本博客参考[蓝猫机场](https://fenfang.org)。转载请注明出处！
