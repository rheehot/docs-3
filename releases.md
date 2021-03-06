# 릴리즈 노트

- [버전 관리 체계](#versioning-scheme)
- [지원 정책](#support-policy)
- [라라벨 5.5](#laravel-5.5)

<a name="versioning-scheme"></a>
## 버전 관리 체계

라라벨의 버전 관리 체계는 다음의 컨벤션을 유지합니다: `paradigm.major.minor`. 메이저 프레임워크 릴리즈는 6 개월마다 (2월, 8월) 릴리즈되며, 마이너 릴리스는 매주 여러번 릴리즈 될 수 있습니다. 마이너 릴리즈에는 이전 버전의 호환성을 깨뜨리는 변경 사항이 **없어야** 합니다.

애플리케이션에서 라라벨 프레임워크, 라라벨의 컴포넌트 또는 패키지를 참조할 때에, 라라벨의 메이저 릴리즈가 이전 버전과 호환성을 유지하지 못하는 변경사항을 포함하고 있기 때문에 항상 `5.5.*` 와 같이 참조하도록 해야 합니다. 변경사항에 대해서는 하루 안에 새로운 릴리즈를 업데이트 할 수 있도록 노력하고 있습니다.

패러다임 변경 릴리즈는 몇년간 구분되어 있으며, 프레임워크의 아키텍처와 컨벤션에 대한 근본적인 변경을 나타냅니다. 현재까지는 개발중인 버전에 대한 변경 발표는 없습니다.

#### 왜 라라벨은 시멘틱 버저닝을 사용하지 않습니까?

한편, 라라벨의 모든 선택가능한 추가 컴포넌트들(Cashier, Dusk, Valet, Socialite, 등)은 시멘틱 버저닝을 **사용**합니다. 그렇지만 라라벨 프레임워크 자체는 그렇지 않습니다.

그 이유는 시멘틱 버저닝이 코드의 두개의 피스가 호환되는지 결정하는 "reductionist" 방법이기 때문입니다. 시멘틱 버저닝을 사용하는 경우라도, 실제로 업그레이드된 패키지를 설치하고 자동화된 테스트를 통해서 *실제* 코드와 호환되지 않는 것이 있는지 확인해야 합니다.

따라서, 그 대신에, 라라벨 프레임워크는 릴리즈의 실제 범위와 관련된 더 많은 정보를 제공하는 버전 관리 체계를 사용합니다. 또한 마이너 릴리즈에는 **절대로** 이전 버전과 호환성을 깨뜨리는 변경사항을 포함하고 있지 않습니다. 여러분이 `paradigm.major.*` 컨벤션을 따르는 한 절대로 이전 버전과 호환되지 않는 사항을 포함하는 변경사항을 적용받지 않습니다.

<a name="support-policy"></a>
## 지원 정책

라라벨 5.5과 같은 LTS 릴리즈 동안에는, 2년간의 버그 픽스와 3년동안의 보안 패치가 지원됩니다. 이러한 릴리즈는 장기간에 걸친 지원과 유지보수를 제공합니다. 일반적인 릴리즈에서는 버그 픽스는 6개월, 보안 패치는 1년동안 제공됩니다.

<a name="laravel-5.5"></a>
## 라라벨 5.5 (LTS)

라라벨 5.5는 패키지 자동 감지, API 리소스 / 데이터변환, 콘솔 명령어의 자동 등록, queued job 체이닝, queued job 의 실행 속도 제한, job 재시도시  제한 시간 지정하기, 브라우저에서 렌더링이 가능한 mailable, exception-예외에 대한 renderable, reportable, 보다 일관된 exceptioin 핸들링, 데이터베이스 테스팅의 강화, 보다 간단해진 커스텀 유효성 검사 rule 등록, React 프론트엔드 preset, `Route::view` 와 `Route::redirect` 메소드, Memcache 와 Redis 캐시의 "잠금" 기능, 일회성 알림 기능, Dusk 에서 headless Chrome 지원, 편리한 블레이드 단축 기능, 신뢰가능한 프록시 지원 향상등 라라벨 5.4에 비해서 기능이 향상되었습니다.

또한 라라벨 5.5는 Redis 기반의 라라벨 queue를 위한 새로운 큐-queue 대시보드및 설정 시스템인 [라라벨 Horizon](https://horizon.laravel.com)와 함께 출시되었습니다.

> {tip} 이 문서는 프레임워크에서 주요한 개선사항들에 대한 요약입니다. 보다 자세한 변경사항은 [GitHub](https://github.com/laravel/framework/blob/5.5/CHANGELOG-5.5.md)에서 확인할 수 있습니다.

### 라라벨 Horizon

Horizon 은 라라벨의 Redis 큐를 위한 멋진 대시보드와 코드 기반의 설정 시스템을 제공합니다. Horizon을 사용하면 작업 처리량, 실행 시간 및 작업 실패와 같은 queue-큐 시스템의 주요 메트릭을 쉽게 모니터링 할 수 있습니다.

모든 워커 설정은 하나의 파일에 저장되므로, 전체 팀이 협업할 수 있는 소스제어시스템을 설정할 수 있습니다.

Horizon 에 대한 보다 자세한 내용은 [전체 Horizon 문서](/docs/{{version}}/horizon)를 참고하십시오.

### 패키지 Discovery

> {video} 이 기능을 설명한 Laracasts 무료 [비디오 강좌](https://laracasts.com/series/whats-new-in-laravel-5-5/episodes/5)를 참고하십시오.

이전 버전의 라라벨에서는 패키지를 설치하려면, 일반적으로 서비스 프로바이더와 파사드를 등록하기 위해서 `app` 설정파일에 몇가지 추가적인 작업들을 진행해야만 했습니다. 하지만 라라벨 5.5 에서는 라라벨이 자동으로 서비스 프로바이더와 파사드를 감지하고, 등록합니다.

예를 들어, 라라벨 애플리케이션에 `barryvdh/laravel-debugbar`를 설치하는 것을 예로 들어 보겠습니다. 컴포저를 통해서 패키지를 설치하고 나면, 추가적인 설정 없이도 애플리케이션에 디버그-바 가 활성화 됩니다:

    composer require barryvdh/laravel-debugbar

패키지 개발자에게 필요한 것은 패키지의 `composer.json` 파일에 서비스 프로바이더와 파사드에 대한 내용을 추가하는 것입니다:

    "extra": {
        "laravel": {
            "providers": [
                "Laravel\\Tinker\\TinkerServiceProvider"
            ]
        }
    },

패키지가 서비스 프로바이더와 파사드를 자동으로 감지하도록 업데이트하기 위한 보다 자세한 내용은 [패키지 개발](/docs/{{version}}/packages)에 대한 전체 문서를 확인하시기 바랍니다.

### API 리소스

API를 구성할 때, Eloquent 모델과 애플리케이션의 사용자에게 전달되는 JSON 응답 사이에 데이터를 변환하는 레이어가 필요할 수도 있습니다. 라라벨의 리소스 클래스는 여러분이 편리하고 손쉽게 모델과 모델 컬렉션을 JSON으로 변환할 수 있게 도와줍니다.

리소스 클래스는 하나의 모델을 JSON 구조에 맞게 변환하여 다시 구성합니다. 예를 들어, 다음과 같은 간단한 `UserResource` 클래스가 있습니다:

    <?php

    namespace App\Http\Resources;

    use Illuminate\Http\Resources\Json\Resource;

    class UserResource extends Resource
    {
        /**
         * Transform the resource into an array.
         *
         * @param  \Illuminate\Http\Request
         * @return array
         */
        public function toArray($request)
        {
            return [
                'id' => $this->id,
                'name' => $this->name,
                'email' => $this->email,
                'created_at' => $this->created_at,
                'updated_at' => $this->updated_at,
            ];
        }
    }

물론 이것은 API 리소스기능의 가장 기본적인 예제 입니다. 라라벨은 리소스와 리소스 컬렉션을 구성할 때 이를 도와줄 수 있는 다양한 메소드를 제공합니다. 보다 자세한 내용은 API 리소스에 대한 [문서](/docs/{{version}}/eloquent-resources)를 참고하십시오.

### 콘솔 명령어 자동 등록

> {video} 이 기능을 설명한 Laracasts 무료 [비디오 강좌](https://laracasts.com/series/whats-new-in-laravel-5-5/episodes/12)를 참고하십시오.

새로운 콘솔 명령어를 생성할 때, 더이상 콘솔 커널의 `$commands` 속성에 수동으로 이를 추가해줄 필요가 없어졌습니다. 대신에 커널의 `commands` 메소드가 새로운 `load` 메소드를 호출하여 주어진 디렉토리에서 콘솔 명령어객체를 찾고 자동으로 등록합니다:

    /**
     * Register the commands for the application.
     *
     * @return void
     */
    protected function commands()
    {
        $this->load(__DIR__.'/Commands');

        // ...
    }

### 새로운 프론트엔드 Presets

> {video} 이 기능을 설명한 Laracasts 무료 [비디오 강좌](https://laracasts.com/series/whats-new-in-laravel-5-5/episodes/4)를 참고하십시오.

라라벨에 여전히 포함되어 있는 기본적인 Vue 스캐폴딩과 같이 몇가지 새로운 프론트 엔드 preset 옵션이 가능해졌습니다. 새롭게 라라벨을 설치하고 나서, `preset` 명령어를 통해서 Vue 스캐폴딩을 React 스캐폴딩으로 변경할 수 있습니다:

    php artisan preset react

또는 `none` preset을 사용하여 자바스크립트와 CSS 프레임워크 스캐폴딩을 완전히 삭제할 수도 있습니다. 이 경우 Sass 파일 하나와 몇가지 자바스크립트 유틸리티를 남겨놓습니다:

    php artisan preset none

> {note} 이 명령어는 새롭게 설치한 라라벨에서만 실행됩니다. 기존 애플리케이션에서는 사용해서는 안됩니다.

### 큐-Queued Job 체이닝

Job 체이닝은 여러분이 queued 로 입력된 job이 순차적으로 실행되도록 목록을 지정할 수 있게 해줍니다. 이 순차적인 목록에서 하나의 job 이 실패하면, 나머지 job은 실행되지 않습니다. job 체이닝을 실행하려면, jobs 에 `withChain` 메소드를 사용하면 됩니다:

    ProvisionServer::withChain([
        new InstallNginx,
        new InstallPhp
    ])->dispatch();

### 유효성 검사 Rule 객체

> {video} 이 기능을 설명한 Laracasts 무료 [비디오 강좌](https://laracasts.com/series/whats-new-in-laravel-5-5/episodes/7)를 참고하십시오.

유효성 검사 Rule 객체는 애플리케이션에 커스텀 validation rule을 추가하는 새롭고 간결한 방법입니다. 이전버전의 라라벨에서는 클로저를 통한 커스텀 validation rule을 추가하기 위해서 `Validator::extend` 메소드가 사용되었습니다. 하지만 이는 매우 귀찮은 작업입니다. 라라벨 5.5에서는 새로운 `make:rule` 아티즌 명령어를 통해서 새로운 유효성 검사-validation rule을 `app/Rules` 디렉토리에 생성할 수 있습니다:

    php artisan make:rule ValidName

rule 객체는 두개의 메소드 : `passes` 와 `message` 를 가지고 있습니다. `passes` 메소드는 속성 값과 이름을 전달받아, 속성 값이 유효한지 아닌지에 따라, `true` 또는 `false` 를 반환해야 합니다. `message` 메소드는 유효성 검사가 실패했을 때 사용하는 에러 메세지를 반환해야 합니다:

    <?php

    namespace App\Rules;

    use Illuminate\Contracts\Validation\Rule;

    class ValidName implements Rule
    {
        /**
         * Determine if the validation rule passes.
         *
         * @param  string  $attribute
         * @param  mixed  $value
         * @return bool
         */
        public function passes($attribute, $value)
        {
            return strlen($value) === 6;
        }

        /**
         * Get the validation error message.
         *
         * @return string
         */
        public function message()
        {
            return 'The name must be six characters long.';
        }
    }

rule 을 정의하고 나면, 다른 유효성 검사 rule 객체들과 함께, rule 객체의 인스턴스를 전달하여, 사용할 수 있습니다.

    use App\Rules\ValidName;

    $request->validate([
        'name' => ['required', new ValidName],
    ]);

### 신뢰 할 수 있는 프록시

TLS / SSL 인증서를 통과하는 로드 밸런서 뒤에서 애플리케이션을 실행할 때 애플리케이션에서 HTTPS 링크가 생성되지 않는 경우가 있을 수 있습니다. 일반적으로 이는 애플리케이션이 포트 80의 로드 밸런서에서 전송되는 트래픽뒤에 위치하며, 보안 링크를 생성해야 한다는 것을 알지 못하기 때문입니다.

이 문제를 해결하기 위해서, 많은 라라벨 사용자들이 Chris Fidao 의 [Trusted Proxies](https://github.com/fideloper/TrustedProxy) 패키지를 실처했었습니다. 이제 이러한 공통의 상황에 대응하기 위해서 Chris의 패키지가 라라벨 5.5에 기본적으로 제공됩니다.

라라벨 5.5 애플리케이션에는 `App\Http\Middleware\TrustProxies` 미들웨어가 기본적으로 포함되어 있습니다. 이 미들웨어는 여러분이 애플리케이션이 신뢰해야 하는 프록시를 손쉽게 설정할 수 있도록 도와줍니다:

    <?php

    namespace App\Http\Middleware;

    use Illuminate\Http\Request;
    use Fideloper\Proxy\TrustProxies as Middleware;

    class TrustProxies extends Middleware
    {
        /**
         * The trusted proxies for this application.
         *
         * @var array
         */
        protected $proxies;

        /**
         * The current proxy header mappings.
         *
         * @var array
         */
        protected $headers = [
            Request::HEADER_FORWARDED => 'FORWARDED',
            Request::HEADER_X_FORWARDED_FOR => 'X_FORWARDED_FOR',
            Request::HEADER_X_FORWARDED_HOST => 'X_FORWARDED_HOST',
            Request::HEADER_X_FORWARDED_PORT => 'X_FORWARDED_PORT',
            Request::HEADER_X_FORWARDED_PROTO => 'X_FORWARDED_PROTO',
        ];
    }

### 일회성 알림

때로는 애플리케이션의 "사용자"가 아닌 누군가에게 알림을 보내고자 할 수도 있습니다. 새로운 `Notification::route` 메소드를 사용하여, 알림이 전달될 정보를 지정할 수 있습니다:

    Notification::route('mail', 'taylor@laravel.com')
                ->route('nexmo', '5555555555')
                ->send(new InvoicePaid($invoice));

### 렌더링이 가능한 Mailables

> {video} 이 기능을 설명한 Laracasts 무료 [비디오 강좌](https://laracasts.com/series/whats-new-in-laravel-5-5/episodes/6)를 참고하십시오.

브라우저에서 보다 빠르게 메일의 디자인을 확인할 수 있도록 Mailables는 이제 라우트에서 바로 반환 할 수 있습니다:

    Route::get('/mailable', function () {
        $invoice = App\Invoice::find(1);

        return new App\Mail\InvoicePaid($invoice);
    });

### Renderable & Reportable Exceptions

> {video} 이 기능을 설명한 Laracasts 무료 [비디오 강좌](https://laracasts.com/series/whats-new-in-laravel-5-5/episodes/18)를 참고하십시오.

이전 버전의 라라벨에서는 exception 핸들러에서 주어진 exception 을 위한 별도의 응답을위해서 매번 "타입 체크"를 했어야만 합니다. 예를 들어 exception 핸들러의 `render` 메소드에 다음과 같은 코드를 작성했을 수 있습니다:

    /**
     * Render an exception into an HTTP response.
     *
     * @param  \Illuminate\Http\Request  $request
     * @param  \Exception  $exception
     * @return \Illuminate\Http\Response
     */
    public function render($request, Exception $exception)
    {
        if ($exception instanceof SpecialException) {
            return response(...);
        }

        return parent::render($request, $exception);
    }

라라벨 5.5 에서는 이제 exception 에 바로 `render` 메소드를 정의할 수 있습니다. 이렇게 하면 exception 에 바로 커스텀 응답을 위한 렌더링 로직을 넣을 수 있어, exception 핸들러에서 매번 exception 을 확인하는 과정을 없앨 수 있습니다. exception 을 보고하는(reporting) 로직을 커스터마이징 하고자 한다면, 마찬가지로 클래스에 `report` 메소드를 정의하면 됩니다:

    <?php

    namespace App\Exceptions;

    use Exception;

    class SpecialException extends Exception
    {
        /**
         * Report the exception.
         *
         * @return void
         */
        public function report()
        {
            //
        }

        /**
         * Report the exception.
         *
         * @param  \Illuminate\Http\Request
         * @return void
         */
        public function render($request)
        {
            return response(...);
        }
    }

### Request 유효성 검사

> {video} 이 기능을 설명한 Laracasts 무료 [비디오 강좌](https://laracasts.com/series/whats-new-in-laravel-5-5/episodes/2)를 참고하십시오.

`Illuminate\Http\Request` 객체는 이제 라우트 클로저나 컨트롤러에서 유입되는 request에 대해 보다 빠르게 유효성 검사를 할 수 있도록 `validate` 메소드를 제공합니다:

    use Illuminate\Http\Request;

    Route::get('/comment', function (Request $request) {
        $request->validate([
            'title' => 'required|string',
            'body' => 'required|string',
        ]);

        // ...
    });

### 보다 일관된 exceptioin 핸들링

이제 유효성 검사의 exception-예외는 이제 프레임워크 전체에서 일관되게 처리됩니다. 이전까지는 JSON 타입의 유효성 검사 에러에 대한 응답의 기본 포맷을 변경하기 위한 작업들이 프레임워크의 여러 곳에 흩어져 있었습니다. 또한 라라벨 5.5에서는 JSON 타입의 유효성 검사 응답-reponse는 다음의 형태를 띄게 됩니다:

    {
        "message": "The given data was invalid.",
        "errors": {
            "field-1": [
                "Error 1",
                "Error 2"
            ],
            "field-2": [
                "Error 1",
                "Error 2"
            ],
        }
    }

`App\Exceptions\Handler` 클래스에 메소드를 정의하여 모든 JSON 타입의 유효성 검사 에러 포맷을 조정할 수 있습니다. 예를 들어, 다음처럼 메소드를 구성하면 JSON 타입의 유효성 검사 응답-response은 라라벨 5.4와 같아집니다.

    use Illuminate\Validation\ValidationException;

    /**
     * Convert a validation exception into a JSON response.
     *
     * @param  \Illuminate\Http\Request  $request
     * @param  \Illuminate\Validation\ValidationException  $exception
     * @return \Illuminate\Http\JsonResponse
     */
    protected function invalidJson($request, ValidationException $exception)
    {
        return response()->json($exception->errors(), $exception->status);
    }

### 캐시 잠금

이제 Redis 와 Memcached 캐시 드라이버는 "잠금-locks"을 구성하고 해제하는 기능을 지원합니다. 이렇게 되면, race condition 을 걱정하지 않고, 임의로 lock을 간단하게 얻을 수 있습니다. 예를 들어, 어떤 작업을 수행하기 전에 lock을 요청할 수 있으므로 다른 프로세스가 현재 진행 중인 동일한 작업을 시도하지 않도록 할 수 있습니다:

    if (Cache::lock('lock-name', 60)->get()) {
        // Lock obtained for 60 seconds, continue processing...

        Cache::lock('lock-name')->release();
    } else {
        // Lock was not able to be obtained...
    }

또는 `get` 메소드에 클로저를 전달 할 수 있습니다. 클로저는 lock을 얻을 수 있고, 클로저가 실행된 이후에 자동으로 lock이 해제되는 경우에만 실행 됩니다:

    Cache::lock('lock-name', 60)->get(function () {
        // Lock obtained for 60 seconds...
    });

또한 lock이 사용가능할때까지 "block" 할 수도 있습니다:

    if (Cache::lock('lock-name', 60)->block(10)) {
        // Wait for a maximum of 10 seconds for the lock to become available...
    }

### 블레이드 개선사항

> {video} 이 기능을 설명한 Laracasts 무료 [비디오 강좌](https://laracasts.com/series/whats-new-in-laravel-5-5/episodes/10)를 참고하십시오.

커스텀 지시어를 프로그래밍하면 간단한 조건문을 정의할 때 필요 이상으로 복잡한 경우가 많습니다. 이 때문에 블레이드는 이제 클로저를 사용하여 커스텀 if 지시어를 보다 빠르게 정의할 수 있는 `Blade::if` 메소드를 제공합니다. 예를 들어 현재 애플리케이션의 구동 환경을 확인하는 커스텀 지시어를 정의하면 다음처럼 `AppServiceProvider` 의 `boot` 메소드에서 사용할 수 있습니다:

    use Illuminate\Support\Facades\Blade;

    /**
     * Perform post-registration booting of services.
     *
     * @return void
     */
    public function boot()
    {
        Blade::if('env', function ($environment) {
            return app()->environment($environment);
        });
    }

커스텀 조건을 정의한 뒤에는, 템플릿에서 손쉽게 사용할 수 있습니다:

    @env('local')
        // The application is in the local environment...
    @else
        // The application is not in the local environment...
    @endenv

블레이드에 커스텀 조건 지시어를 쉽게 정의할 수 있는 기능 외에도, 새로운 단축 기능이 추가되어 현재 사용자의 인증여부를 빠르게 확인할 수 있습니다:

    @auth
        // The user is authenticated...
    @endauth

    @guest
        // The user is not authenticated...
    @endguest

### 새로운 라우팅 메소드

> {video} 이 기능을 설명한 Laracasts 무료 [비디오 강좌](https://laracasts.com/series/whats-new-in-laravel-5-5/episodes/16)를 참고하십시오.

다른 URI로 이동시키는 라우트를 정의했었다면, 이제 `Route::redirect` 메소드를 사용할 수 있습니다. 이 메소드는 손쉬운 방법을 제공합니다. 이 메소드는 간단한 리다이렉트를 위해서 복잡한 라우트나 컨트롤러 전체를 정의하지 않아도 되는 편리한 방법을 제공합니다:

    Route::redirect('/here', '/there', 301);

단지 뷰를 반환하기만 하는 라우트가 필요하다면, 이제 `Route::view` 메소드를 사용할 수 있습니다. `redirect` 메소드와 같이 이 메소드는 간단한 리다이렉트를 위해서 복잡한 라우트나 컨트롤러 전체를 정의하지 않아도 되는 편리한 방법을 제공합니다. `view` 메소드는 첫번째 인자로 URI를, 두번째 인자로 뷰 파일의 이름을 전달 받습니다. 또한 이에 더해, 세번째 인자로 view 에 제공할 데이터들의 배열을 제공할 수도 있습니다:

    Route::view('/welcome', 'welcome');

    Route::view('/welcome', 'welcome', ['name' => 'Taylor']);

### "Sticky" 데이터베이스 커넥션

#### `sticky` 옵션

읽기 / 쓰기 데이터베이스 커넥션을 구분해서 구성할 때, 새로운 `sticky` 설정 옵션을 사용할 수 있습니다:


    'mysql' => [
        'read' => [
            'host' => '192.168.1.1',
        ],
        'write' => [
            'host' => '196.168.1.2'
        ],
        'sticky'    => true,
        'driver'    => 'mysql',
        'database'  => 'database',
        'username'  => 'root',
        'password'  => '',
        'charset' => 'utf8mb4',
        'collation' => 'utf8mb4_unicode_ci',
        'prefix'    => '',
    ],

`sticky` 옵션은 현재 request-요청사이클 에서 데이터베이스에 기록된 레코드를 바로 읽을 수 있도록 하는 *있어도 되고 없어도 되는* 값입니다. `sticky` 옵션이 활성화 되어 있고 현재 request-요청사이클에서 데이터베이스에 "쓰기" 작업을 수행한 경우 이 뒤에 "읽기"작업은 "쓰기"에서 사용한 커넥션으르 사용합니다. 이렇게 되면, request-요청사이클 동안에 작성된 모든 데이터를 동일한 request-요청 중에서는 바로 데이터베이스에서 읽을 수 있습니다. 여러분의 애플리케이션에서 이러한 동작이 필요한지에 대해서 결정하는 건 여러분의 선택에 따라 달라질 수 있습니다.
